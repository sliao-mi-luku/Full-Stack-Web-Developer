# psycopg2

last updated: 05/02/2021

---

## psycopg2

[psycopg2 documentation](https://www.psycopg.org/docs/index.html)

## Install psycopg2

Before that, update pip first
```
$ pip install -U pip
```

Install psycopg2:
```
$ pip install psycopg2-binary
```

## psycoph2 basics

Below are the pythons codes to connect an existing database (whose name is `example_db`) with psycopg2

Notes: the `example_db` has no tables inside.

```python
import psycopg2

# create the connection object
conn = psycopg2.connect('dbname=example_db')

# select the cursor
cur = conn.cursor()

# create a table named example_table
cur.execute("""
  CREATE TABLE example_table (
      id INTEGER PRIMARY KEY,
      status BOOLEAN NOT NULL DEFAULT False
  );
""")

# insert a row
cur.execute("INSERT INTO example_table (id, status) VALUES (1, true);")

# commit
conn.commit()

# close the cursor
cur.close()

# close the connection
conn.close()
```


