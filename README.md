# How to run

## Generate a new virutal environment
```shell
python -m venv venv
```

## Activate the environment
```shell
.\venv\Scripts\activate
```

## Install all libraries in requirements.txt
```shell
pip install -r .\requirements.txt 
```

## Run flask app
```shell
flask --app flaskr run

# Run with debug mode
flask --app flaskr run --debug
```

# Project Structure
```shell
│   .gitignore
│   pyproject.toml
│   README.md
│   requirements.txt
│   sqlite_query.sql
│   tree.txt
│
├───flaskr
│   │   auth.py
│   │   blog.py
│   │   db.py
│   │   schema.sql
│   │   __init__.py
│   │
│   ├───static
│   │       style.css
│   │
│   └───templates
│       │   base.html
│       │
│       ├───auth
│       │       login.html
│       │       register.html
│       │
│       └───blog
│               create.html
│               index.html
│               update.html
│
└───instance
        flaskr.sqlite
```