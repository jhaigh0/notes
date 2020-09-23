# Postgresql Notes

### Config files

First there were 2 config files to change.

- `HOME=/var/lib/pgsql`
- `$HOME/data/postgresql.conf`
- `$HOME/data/pg_hba.conf`

#### postgresql.conf

Uncomment the line `listen_addresses = 'localhost'` 

#### pg_hba.conf

Change the `METHOD` on row `local` to `md5`



### Creating user and database 

**First start service is needed**

```
~ systemctl start postgresql.service
```



**Create a database like this**

```
~ sudo -u postgres createdb <db_name>
```

`sudo -u postgres` means to do the command as the unix user `postgres` which is created when postgresql is installed. It's not needed if already in the terminal as user `postgres`



**Create user like this**

```
~ sudo -u postgres createuser --no-createrole --no-superuser --pwprompt <user_name>
```

(optional tags were used on Ag's  postgres setup advice)



#### Connecting to database

**To access database**

```
~ psql -U <user_name> <db_name>
<db_name>=> _
```

- `\l` to list databases
- `\d` to list relations
- `\?` to all list postgres commands





