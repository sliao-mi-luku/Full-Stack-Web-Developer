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

3. Go back to the terminal 

```
$ FLASK_APP=flask-hello-app.py flask run
```

4. The URL will be displayed on the terminal. Copy that URL and paste to a browser to see the homepage.
