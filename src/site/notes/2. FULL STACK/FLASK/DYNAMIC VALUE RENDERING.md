---
{"dg-publish":true,"permalink":"/2-full-stack/flask/dynamic-value-rendering/","noteIcon":""}
---

#flask #python 
- Use the **`render_template`** to render the *HTML* Page.
- Using *Jinja2* lang you can create a **`variable`** - `{{variable_name}}` 
- You can add as many variables you want in **`render_template()`** method.
```HTML 
<html lang="en">
    <head>
        <title>Home Page</title>
    </head>
    <body>
        <h1>Home Page!</h1>
        <p>{{content}}</p>
    </body>
</html>
```

```Python 
from Flask import Flask

app = Flask(__name__)

@app.route("/<name>")
def admin():
	return render_template ("index.html", content=name)

if __name__ == "__main__":
	app.run(debug=True)
```

- Here, the **`content`** is the variable used in frontend. 
- We pass `content` to the **`render_template()`** method referring the value used in the **URI** variable (`name`).
****
## USING PYHTON IN HTML 
- Using **`{% Python_code %}`** python in HTML. 
- **`{{ var_name }}`** - is used to print the variable. 
- Passing the list.
```Python 
from Flask import Flask

app = Flask(__name__)

@app.route("/<name>")
def admin():
	return render_template ("index.html", content=[Shane, Kimberly, Nick, Joe])

if __name__ == "__main__":
	app.run(debug=True)
```

```HTML 
<html lang="en">
    <head>
        <title>Home Page</title>
    </head>
    <body>
    {% for x in 10 %}
	    {% if in content %}
		    <p>{{x}}</p> 
	{% endfor %}
    </body>
</html>
```
***
***
 