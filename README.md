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

## Install DB Schema
```shell
flask --app flaskr init-db
```

## Run flask app
```shell
flask --app flaskr run

# Run with debug mode
flask --app flaskr run --debug
```

# Database
## SQLITE
SQLite is an embedded SQL database engine. Unlike most other SQL databases, SQLite does not have a separate server process. SQLite reads and writes directly to ordinary `disk files`.

## Tables
Basic database tables are defined in `.\flaskr\schema.sql`
```sql
DROP TABLE IF EXISTS user;
DROP TABLE IF EXISTS post;

CREATE TABLE user (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  username TEXT UNIQUE NOT NULL,
  password TEXT NOT NULL
);

CREATE TABLE post (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  author_id INTEGER NOT NULL,
  created TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
  title TEXT NOT NULL,
  body TEXT NOT NULL,
  FOREIGN KEY (author_id) REFERENCES user (id)
);
```

## Extension/Plugins
### Visual Studio Code

### PyCharm


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