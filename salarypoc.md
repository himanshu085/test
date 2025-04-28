# Salary-API Documentation

## Installation of Application

```bash
sudo apt update
```

---

## Installation of Prerequisites

### ScyllaDB Installation and Configuration

```bash
sudo mkdir -p /etc/apt/keyrings
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys A43E06657BAC99E3
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.2.list
sudo apt-get update
sudo apt-get install -y scylla
sudo /opt/scylladb/scripts/scylla_io_setup
```

Update the configuration:

```bash
sudo vi /etc/scylla/scylla.yaml
```

Set:

```yaml
authenticator: PasswordAuthenticator
authorizer: CassandraAuthorizer
rpc_address: <private_IP>
```

Restart and check service:

```bash
sudo systemctl restart scylla-server.service
sudo systemctl status scylla-server
```

Connect:

```bash
cqlsh <private_IP> 9042 -u cassandra -p cassandra
```

Create user and keyspace:

```sql
CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };
DESCRIBE KEYSPACES;
```

---

### Redis Installation and Configuration

Install Redis:

```bash
sudo apt update
sudo apt install redis-server -y
```

Configure user:

```bash
redis-cli
ACL SETUSER scylla on >password ~* +@all
ACL LIST
exit
```

Update Redis config:

```bash
sudo vi /etc/redis/redis.conf
```

Add:

```
bind 127.0.0.1 <private_IP>
```
like this bind 127.0.0.1 172.31.25.109 ::1
comment out by adding # bind 127.0.0.1 ::1

Restart Redis:

```bash
sudo systemctl restart redis
```

Check Redis connection:

```bash
redis-cli -h <private_IP> -p 6379 ping
```

---

### Install Maven & Java Dependencies

```bash
sudo apt install openjdk-17-jre
sudo apt install maven -y
```

---

### Installation of Swagger

```bash
sudo apt install jq -y
download_url=$(curl -s https://api.github.com/repos/go-swagger/go-swagger/releases/latest | jq -r '.assets[] | select(.name | contains("'"$(uname | tr '[:upper:]' '[:lower:]')"'_amd64")) | .browser_download_url')
sudo curl -o /usr/local/bin/swagger -L "$download_url"
sudo chmod +x /usr/local/bin/swagger
```

---

## Clone Salary-API Repository

```bash
git clone https://github.com/OT-MICROSERVICES/salary-api.git
cd salary-api/
```

Update private IPs:

```bash
sudo vi src/main/resources/application.yml
sudo vi src/test/resources/application.yml
```

---

## Create Service File for Salary-API

Create:

```bash
sudo vi /etc/systemd/system/salary-api.service
```

Content:

```ini
[Unit]
Description=salary api
After=network.target

[Service]
Type=simple
User=ubuntu
Group=ubuntu
WorkingDirectory=/home/ubuntu/salary-api/
ExecStart=java -jar /home/ubuntu/salary-api/target/salary-0.1.0-RELEASE.jar --server.port=8081
Restart=on-failure
RestartSec=5
StandardOutput=journal
StandardError=journal

[Install]
WantedBy=multi-user.target
```

Enable and start:

```bash
sudo systemctl enable salary-api.service
sudo systemctl start salary-api.service
```

---

## Install Migration Tool

```bash
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz | tar xvz
sudo mv migrate /usr/local/bin/migrate
migrate --version
```

Update IPs:

```bash
sudo vi src/main/java/com/opstree/microservice/salary/config/OpenAPIConfig.java
sudo vi src/test/java/com/opstree/microservice/salary/config/OpenAPIConfigTests.java
sudo vi migration.json
```

---

## Run Java Runtime Command

Package:

```bash
mvn clean package
```

Install make:

```bash
sudo apt install make
```

Run migrations:

```bash
make run-migrations
```

Start Java app:

```bash
java -jar target/salary-0.1.0-RELEASE.jar
```

---

## Output
 Hit with public ip like this 
```sh
http://52.90.125.211:8080/swagger-ui/index.html
```

## Error Handling

**Error**: Port already in use.

**Fix**:

```bash
sudo lsof -i :8080
sudo kill -9 <pid>
java -jar target/salary-0.1.0-RELEASE.jar
```
