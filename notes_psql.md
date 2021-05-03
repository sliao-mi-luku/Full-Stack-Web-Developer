# psql notes

last updated: 05/02/2021

## Log into Postgres

Log in with a particular user name:

```terminal
sudo -u <username> -i
```

For example: `sudo -u postgres -i`

## Create/Delete database

To create a database:
```psql
createdb <database_name>
```

To delete a database:
```psql
dropdb <database_name>
```

## Connect a database

You can connect a database by:
```terminal
$ psql <database_name>
```

After passing in this command, you will see the command line becomes `<database_name>=#`. You can use SQL commands after the # sign.

### psql commands

Besides basic SQL commands, the commands below might be useful (you can also use `\?` to see all available commands):

| Command | Description |
| ----------- | ----------- |
| `\l` | list all dbs and owners |
| `\c <database_name>` | connect to database_name |
| `\dt` | list all tables under the current database |
| `\d <table_name>` | show the schema of table_name |
| `\q` | quit psql |
