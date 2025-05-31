### PSQL Database

https://www.postgresql.org/download/linux/ubuntu/

Connect the repo

```
sudo apt install -y postgresql-common
sudo /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh
```

Install specific version

```
sudo apt install postgresql-16
```

Check Version

```
psql --version
pg_config --version
```

Start PSQL Server in background

```
sudo systemctl start postgresql
sudo systemctl enable postgresql
```

Go into PSQL

```
sudo -i -u postgres
psql
```

Create Database

```
CREATE DATABASE test_app;
CREATE ROLE test_user WITH LOGIN PASSWORD 'test_password';
GRANT ALL PRIVILEGES ON DATABASE "test_app" TO test_user;
```

List current active

```
\l
```

quit

```
\q
exit
```

Allow remote connections to PostgreSQL on Linux

/etc/postgresql/<version>/main directory. For example, if you install PostgreSQL 16, the configuration files are stored in the /etc/postgresql/16/main directory.

```
cd /etc/postgresql/16/main
```

```
 sudo cp postgresql.conf postgresql.conf.bak
```

```
sudo nano postgresql.conf
```

```
sudo nano pg_hba.conf
```

![alt text](image.png)

```
sudo ufw allow 5432/tcp
```

or on oracle allow port, also allow port on security rules

```
sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 80 -j ACCEPT
sudo netfilter-persistent save
sudo systemctl restart apache2
```

https://blog.devart.com/configure-postgresql-to-allow-remote-connection.html