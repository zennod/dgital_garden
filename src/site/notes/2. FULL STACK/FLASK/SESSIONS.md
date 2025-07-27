---
{"dg-publish":true,"permalink":"/2-full-stack/flask/sessions/","noteIcon":""}
---

#flask #python 
- Session basically means the *user activity* on the web-app. They are temporary
# WORKING 
The **user session** is maintained & tracked interaction across multiple pages.
# EXAMPLE
User logs in & the *SESSION* is stored in the server. 
- It's mostly use to give user *quick access* to there information.
***
- In Flask, we *store the information* the **SESSION**, Just by `importing` the `session` module & adding - **`session["session_key"] = session_value`** in the code. 
- Also, you need to add the **`secret_key`** for the ensuring the encryption & decryption of the information.
```Python 
from flask import session

app.secret.key = "dsds"

@app.route('/set_session')
def set_session():
    session['key'] = 'value'
    return "Session variable set!"

```
***
# USING THE SESSION

- You can use the **SESSION** by verifying the information of the *user name*. 
- The below example is not the actual scenario.

```Python 
from flask import session

@app.route('/set_session')
def set_session():
    session['key'] = 'value'
    return "Session variable set!"

@app.route('/get_session')
def get_session():
    return session.get('key', 'Not set')

```

***
# CLEARING THE SESSION

- Clearing the session when not needed is the most important part. 
- Using **`session.pop("key", None)`**
	- With this you can remove *selective item from session*.
```Python
@app.route("/logout")
def logout():
    session.pop("user", None)
    return redirect(url_for("login"))
```

- Also, there's **`session.clear`**
	- Using this,  you can *clear* the session - refer to the *complete reset of session data.*

***
# ACTUAL USE CASE 
```Python 
from flask import Flask, session, redirect, url_for, request, render_template

app = Flask(__name__)
app.secret_key = 'your_very_secret_key'  # Replace with a real secret key

# Dummy user data, typically this would be in a database
users = {
    'admin': 'secret',
    'user': 'pass'
}

@app.route('/')
def index():
    if 'username' in session:
        return f'Logged in as {session["username"]}'
    return 'You are not logged in'

@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        username = request.form['username']
        password = request.form['password']
        if username in users and users[username] == password:
            session['username'] = username
            return redirect(url_for('index'))
        return 'Invalid username or password'
    return render_template('login.html')  # Assuming a template with a login form


@app.route('/logout')
def logout():
    session.pop('username', None)
    return redirect(url_for('index'))

if __name__ == '__main__':
    app.run(debug=True)

```

***
***
# PERMANENT SESSION 
- We can decide that how long we want the **SESSION** to be stored. 
- We can do it by using the **`app.permanent_session_lifetime`**
## STEPs 
1.  Use **`datetime`** library with **`timedelta(time_in_Day_Hour_Min)`** to set the time for the session.
```Python
from datetime import timedelta
app.permanent_session_lifetime = timedelta(hours=4)
```

2. Setting the *permanent session* 
	- Use **`session.permanent = True`** to set it.
```Python
@app.route("/user")
def user():
    if "user" in session:
        session.permanent = True
        return render_template("user.html", user=session["user"])
    else:
        return redirect(url_for("login"))
```
