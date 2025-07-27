---
{"dg-publish":true,"permalink":"/2-full-stack/flask/template-inheritance/","noteIcon":""}
---

#flask #python 

- The **TEMPLATE INHERITANCE** comes handy when the website has same *NavBar, Header & Footer* in every single page. 
- So, to use it we'll create a HTML file named **`base.html`** 
- **`base.html`** acts as **PARENT CLASS** (which has the properties - *NavBar, Header & Footer*)
- And, Lastly we will inherit it to the **`index.html`**
***
- To use **TEMPLATE INHERITANCE** add *block* in the **PARENT CLASS** (i.e. **`base.html`**)

``` HTML
// base.html
<html lang="en">
    <head>
        <title>{% block title %} {% endblock%}</title>
    </head>
    <body>
        <p>{{content}}</p>
    </body>
</html>
```

- Now, to **extend** the **PARENT CLASS** in the **CHILD CLASS**.
	- Use **`{% extends "parent_class_fileName" %}`**
```HTML
{% extend "base.html" %}
{% block title %} 
	Home Page
{% endblock%}
```
- Using the **`{% extends "parent_class_fileName" %}`** in any `.html` file. 
- You can use the content of the `base.html`