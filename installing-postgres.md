# Install Java 
`sudo apt-get update`
`sudo apt-get openjdk-17-jre`


**Allow all trafic in the security groups in ec2 machine**

# Run the following command to install postgres database
`sudo apt update`  
`sudo apt -y install postgresql`
`sudo systemctl start postgresql`  
`sudo systemctl enable postgresql ` 
`sudo systemctl status postgresql` 

**Normally the postgres database is not listen in for requests from outside, to enable that:**  

<!-- # take a backup of the below file
sudo cp /var/lib/pgsql/data/postgresql.conf /var/lib/pgsql/data/postgresql.conf.bak -->

### modify the file to accept connections from anywhere.
`sudo nano etc/postgresql/16/main/postgresql.conf`

### change the following in the above file
`listen_addresses = '*' `

### now change the password of the postgres user 
`sudo passwd postgres`

### Login using Postgres system account-
`su - postgres`

### Now, change the database postgres password
`psql -c "ALTER USER postgres WITH PASSWORD 'postgres';"`


Create a new database and user:

sql

CREATE DATABASE mydatabase;
CREATE USER myuser WITH PASSWORD 'mypassword';



### exit from this user
`exit`

### modify the following file to allow remote connections
`sudo nano /var/lib/pgsql/data/pg_hba.conf`

### change the below lines in the conf file

#host    all             all             127.0.0.1/32            scram-sh256
host    all             all             0.0.0.0/0           md5 


or 

host    all             all             0.0.0.0/0           trust
host    all             all             ::/0           trust

### restart the database
sudo systemctl restart postgresql




### CLI postgress

* su - postgres

* psql

* /list

* /c student 