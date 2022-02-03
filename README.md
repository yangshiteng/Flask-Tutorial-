# Flask-Tutorial

https://code.visualstudio.com/docs/python/tutorial-flask

Flask is a lightweight Python framework for web applications that provides the basics for URL routing and page rendering.

## 1. app.py (python -m flask run or ctrl+F5 debug)

from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello, Flask!"
    
@app.route("/hello/<name>")
def hello_there(name):
    now = datetime.now()
    formatted_now = now.strftime("%A, %d %B, %Y at %X")

    # Filter the name argument to letters only using regular expressions. URL arguments
    # can contain arbitrary text, so we restrict to safe characters only.
    match_object = re.match("[a-zA-Z]+", name)

    if match_object:
        clean_name = match_object.group(0)
    else:
        clean_name = "Friend"

    content = "Hello there, " + clean_name + "! It's " + formatted_now
    return content
