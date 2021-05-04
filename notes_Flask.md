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
