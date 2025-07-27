---
{"dg-publish":true,"permalink":"/2-full-stack/flask/data-retrieval-via-http/","noteIcon":""}
---

#flask #python #http 
[[4. PERSONAL/1. CompTIA Network+/06. TCP_IP/6.1 TCP_IP BASICS/6.1.1 TCP_IP PROTOCOL SUITE/3. APPLICATION LAYER PROTOCOL (HTTP_HTTPS HEADER)\| HTTP METHODS]]

- We can **RETRIEVE/SEND** the *data* from the server using the *HTTP METHODS* in *FLASK*.
- To use *Multiple Methods* on a page use it in **LIST `[method1, method2,...,methodN]`**
- To use HTML content in the flask, use `request` module of the Flask library.

```HTML 
{% extends "base.html"%}
{% block title%} Login Page {%endblock%}


{% block content%} 
<form action="#" method="post">
  <p>Name: </p>
  <p><input type="text" name ="nm" </p>
  <p><input type="submit" value="submit"</p>
</form>
{%endblock%}
```



```Python
from Flask import Flask,render_template, request, redirect, url_for

app = Flask(__name__)

@app.route("/home"):
def home():
	return "Hello! <h1>This is the Home Page</h1>"

@app.route('/login', methods=["POST", "GET"])
def login():
    if request.method == "POST":
        user = request.form["nm"]
        return redirect(url_for("user", usr=user))
    else:
        return render_template("login.html")

@app.route("/<usr>")
def user(usr):
    return f"<h1>{usr}</h1>"

if __name__ == "__main__":
	app.run(debug=True)
```