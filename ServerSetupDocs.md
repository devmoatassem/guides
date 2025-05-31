### Setup EC2 Instance

```bash
sudo apt update
sudo apt upgrade
```

### Install Node.js v20.0 LTS

```
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
```

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

### Other Commands to Check system usage

Check free memory

```
free -h
```

Current CPU usage

```
top
```

htop for more dynamic view

### pm2 install globally

https://chatgpt.com/share/d1b66fbb-6aa7-42c7-9910-11356c3f6191

### next js with pm2

https://chatgpt.com/share/175638d4-24cc-4496-a2ff-5403ad358b6f

###
