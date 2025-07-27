---
{"dg-publish":true,"permalink":"/2-full-stack/flask/rout-es-and-redirect/","noteIcon":""}
---

#flask #python 

# ROUTEs
- It can be defined simply by using the **DECORATOR** **`@app.route("/route_name")`**
- The below is the **`/home`** route *example*.
```Python 
from Flask import Flask,

app = Flask(__name__)

@app.route("/home"):
def home():
	return "Hello! <h1>This is the Home Page</h1>"

if __name__ == "__main__":
	app.run(debug=True)
```
***
# RE-DIRECT 
- You can use the module from the **`Flask`** Library. 
```Python 
from Flask import Flask, redirect, url_for

app = Flask(__name__)

@app.route("/home"):
def home():
	return "Hello! <h1>This is the Home Page</h1>"

@app.route("/admin")
def admin():
	return redirect(url_for("home"))

if __name__ == "__main__":
	app.run(debug=True)
```
***
***
