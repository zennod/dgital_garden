---
{"dg-publish":true,"permalink":"/2-full-stack/flask/message-flashing/","noteIcon":""}
---

#flask #python 
- It refers to the *action of previous page is previewed to the next page*.
# STEPs 
1. To perform this you need to use the library called **`flash`**
```Python 
from flask import flash
```
2.  Add the `flash("message", "category")` method in the code to use the message flashing
```Python
flash("Logged Out", "info")
```
3. **Displaying the message** - The Below code is used in HTML to display the message on the page 
```HTML 
{%with messages = get_flashed_messages() %}
{% if messages %}
  {%for msg in messages%}
	<p>{{msg}}</p>
  {% endfor %}
{% endif %}
{% endwith %}
```
***
# USE - CASE SCENERIO
```Python
from datetime import timedelta

from flask import Flask, redirect, render_template, request, session, url_for
from flask.helpers import flash


app = Flask(__name__)
app.secret_key = "hello"

app.permanent_session_lifetime = timedelta(minutes=2)


@app.route('/')
def index():
    return render_template('index.html')


@app.route('/login', methods=["POST", "GET"])
def login():
    if request.method == "POST":
        username = request.form["nm"]
        session["user"] = username
        flash("Log in Successful.")
        return redirect(url_for("user"))
    else:
        if "user" in session:
            flash("Already Logged in")
            return redirect(url_for("user"))
        return render_template("login.html")


@app.route("/user")
def user():
    if "user" in session:
        session.permanent = True
        return render_template("user.html", user=session["user"])
    else:
        flash("You are not logged in..!!")
        return redirect(url_for("login"))


@app.route("/logout")
def logout():
    if "user" in session:
        user = session["user"]
        flash(f"You have been logged out {user}")
    session.pop("user", None)
    return redirect(url_for("login"))


if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000, Debug=True)

```