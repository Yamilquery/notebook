# Postgres

Postgres uses a client/server model:

1. A server, which manages database files, accepts connections, and acts upon the database. The database server program is called `postmaster`.

2. The client's (frontend) application.

The server forks a new server process for each client connection. `postmaster` is always running, while client and server processes come and go.

    database cluster => database => tables => rows & columns


## Creating & removing a database

```sh
$ createdb dbname
$ dropdb dbname
```



## Dumping and restoring a database

```sh
$ pg_dump -O dbname > outfile
```

If you'd like to compress it:

```sh
$ pg_dump -O dbname | gzip > filename.gz

$ dropdb dbname
$ createdb -T template0 dbname
$ psql dbname < infile
```



## Using psql

```sh
$ psql [dbname]
```

```sql
\q              # quit psql
\?              # list psql commands

\i [file]       # execute commmands found in a file
\o [file]       # send all query results to file or |pipe

\d              # list all tables in database
\di             # list all indices

\cd             # change current working directory
\! [command]    # execute command in shell or start interactive shell
```



## Importing/Exporting with CSV

Import from a CSV:

```sh
$ copy users(name, email) from '/Users/john/users.csv' delimiter ',' CSV;
```

Export to a CSV:

```sh
$ copy (select * from users) to '/Users/john/users.csv' with CSV;
```
