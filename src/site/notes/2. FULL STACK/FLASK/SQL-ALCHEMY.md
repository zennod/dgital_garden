---
{"dg-publish":true,"permalink":"/2-full-stack/flask/sql-alchemy/","noteIcon":""}
---

#flask #python 
- SQL Alchemy is used as the database generator. 

# STEPs 
1. Import & Configuration of SQLAlchemy & Database.
```Python
from flask_sqlalchemy import SQLAlchemy

app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///table_name.sqlite3'
app.config['SQLALCHEMY_TRACK_MODIFICATION'] = False
```

2. Starting point of the Database
```Python 
db = SQLAlchemy(app)
```

3. Creating Model to store information
	- To create a model you need to make a **CLASS** *of the table*
	- **`var = db.Column("name _of_col", db.datatype, primary_key=True )`**
	- Adding **`db.create_all()`** - to *creates the table* if it doesn't exist in the *Database*.

```Python
@app.before_request
def create_tables():
    db.create_all()

# Creating the class for the table
class users(db.Model):
    # Creating Attributes for table
    _id = db.Column("id", db.Integer, primary_key=True)
    name = db.Column("name", db.String(no_of_char))

    # Setting the DB variable
    def __init__(self,name, email) -> None:
        self.name = name
        self.email = email

# Creates table
if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000, Debug=True)
```

4. **CREATING DATA** -
```Python
        found_user = users.query.filter_by(attribute=local_var).first()
        #Create user 
        if found_user:
            session["key"] = found_user.value
        else: 
		var_name = table_name(attributes)
		db.session.add(var_name)
		db.session.commit()
```

5. **DELETING DATA**
	- For single value use 
		- **`users.query.filter_by(attribute=local_var).first()`**
```Python
        found_user = users.query.filter_by(attribute=local_var).delete() 
        if found_user:
            session["key"] = found_user.value
        else: 
		var_name = table_name(attributes)
		db.session.add(var_name)
		db.session.commit()
```

- For deleting multiple records just add an **for loop**
```Python 
        found_user = users.query.filter_by(attribute=local_var).delete()
		for user in found_user:
			user.delete() 
        if found_user:
            session["key"] = found_user.value
        else: 
		var_name = table_name(attributes)
		db.session.add(var_name)
		db.session.commit()
```