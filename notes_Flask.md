# Flask

last updated: 05/03/2021

References:

1. Udacity's Full Stack Web Developer Nanodegree Program

---

## Install Flask

```
$ pip3 install flask
$ pip3 install flask-sqlalchemy
```

## Import Flask (Python)

```python3
from flask import Flask
from flask_sqlalchemy import SQLAlchemy
```

## Hello World Flask App

1. Create a Flask app python file from the terminal (here called `flask-hello-app.py`)

```
$ touch flask-hello-app.py
```

2. Edit the `flask-hello-app.py` (for example, with VSCode)

```python3
# import flask
from flask import Flask

# create a flask application
app = Flask(__name__)

# use @app decorator to specify homepage ('/') as the endpoint to listen to
@app.route('/')
def index(): # the route handler telling what to do next
  return "Hello World!"
```

3. Go back to the terminal to load the app

```
$ FLASK_APP=flask-hello-app.py flask run
```

For live reload, use:

```
$ FLASK_APP=flask-hello-app.py FLASK_DEBUG=true flask run
```

Or, send the commands before `flask run`:

```
$ export FLASK_ENV=development
```

4. The URL will be displayed on the terminal. Copy that URL and paste to a browser to see the homepage.

## Hello World Flask App (2)

```python3
"""
app.py
"""

from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
  return "Hello World!"
  
if __name__ == '__main__':
  app.run(host = '0.0.0.0',
          port = 5000,
          debut = True)
```

```
$ python3 app.py
```

## Flask-SQLAlchemy

**Database connection URI parts**

The `app.config['SQLALCHEMY_DATABASE_URI']` should be set to the string as the format below:

`postgresql://username:password@hostaddress:port/databasename`

notes: `password` is optional


**codes**

```python3
from flask import Flask
from flask-sqlalchemy import SQLAlchemy

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://username@localhost:5432/example_db'
db = SQLAlchemy(app)

# create a Person class
class Person(db.Model):
  # specify the table name 
  __tablename__ = 'persons'
  # create a column to match 'id' in the databse
  id = db.Column(db.Integer, primary_key=True)
  # create a column to match 'name' in the database
  name = db.Column(db.String(), nullable=False)

# create all tables if not exists
db.create_all()

@app.route('/')
def index():

  # fetch the table
  person = Person.query.first()
  # say hello to the person
  return "Hello " + person.name


```

## Interactive Mode

1. In the `app.py` file, add this line:

```python3
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
```

2. In the terminal type python3 to start the interactive mode

```
$ python3
```

3. In the interactive mode, import the app.py file

```
>>> import app
```

4. Import the table class (here called `Person`) and see the contents by:

`<class>.query.all()`
`<class>.query.first()`
`<class>.query.filter(<class>.<attribute> = attribute_name).first()`

```
>>> from app import Person
>>> Peson.query.all()
```




















