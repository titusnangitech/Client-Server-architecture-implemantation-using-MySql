# Implementing a Client-Server Architecture using MySQL Database Management System (DBMS)


![client-server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/12d002f3-b7ca-4cef-9ac3-ad26af45ed2d)




- **Created 2 ec2 instances i.e mysql client and mysql server**


![new ec2 instances created](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/c562a1b0-4de2-4597-82ab-2eef6b6a3187)


- **MySQL server uses TCP port 3306 by default,so i opened it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Group. For extra security, i did not allow all IP addresses to reach my ‘mysql server’ – I allowed access only to the specific local IP address of my ‘mysql client’.**
  
![edited sg inbound rule](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/1fbdc8dd-f198-41c7-ba50-6bb9e285ab7a)

- **Populated the Mobaxterm with the mysql client details**
  
![populating client details](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/96122dbc-33ff-4733-8f32-4937b3a46b2f)

- **Populated the Mobaxterm with the mysql server details**

![populate mobaxterm for server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/ea0dcc84-1fb7-4551-8077-e587443d586e)

- **Connected to the mysql client and switched to root**

 ```
  sudo -i
  ```
  
![connected to client and swiched to sudo](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/2a9e9868-dfd2-44a3-afc4-758a26c13aa5)

- **Connected to the mysql server and switched to root**

```
sudo -i
```

![connected to the DB server and swicthed to sudo](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/dbfaee87-0e40-4d45-8c84-ea0e64ce80f6)

- **update the apt peckage on the mysql server**
  
 ```
  apt update -y
  ```
![apt update for server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/bfdc6ecd-dcb9-42bf-9dc9-202bf25f0eae)

 - **Install MySQL Server Software on the mysql server**
 ```
 apt install mysql-server

```
![apt install mysql on the server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/bcd9e64e-3511-41b0-a1f1-61c0232b306d)

- **Enable mysql on the mysql server**

```
systemctl enable mysql
```

![enable mysql-server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/fd7fb660-3dcd-4dd7-a16f-e8d8ab72a911)


- **Secured mysql server**
  
![securing mysql server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/b23b2bc5-490e-4688-9158-03eee20f8111)

- **Connecting into mysql**

  ```
  mysql
  ```

![connecting to msql using mysql command](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/f0ac6b29-aa04-48f5-91b5-bc621249e653)

- **Created User and Database within the mysql-server**

```
# Created User
 CREATE USER `remote_user`@`%` IDENTIFIED WITH mysql_native_password BY `password`;

# Created database
CREATE DATABASE test_db;

# Grant privileges
GRANT ALL ON test_db* TO `remote_user`@`%`WITH GRANT OPTION; 
```
  

![create user and database within the server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/3d1ce686-d46b-4fe2-9d95-426a89e2d8c6)

- **configure MySQL server to allow connections from remote hosts.**

```
  sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf
```


![changing the msql file in th etc folder though vi](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/2b79609c-8352-4f28-a593-15ab513cc307)

- **Replace ‘127.0.0.1’ to ‘0.0.0.0’**

  
![editing the sql file using vi](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/db48364d-af0e-49a8-856d-2fe228cc5bc5)



- **Restart mysql**

  
![restart sql](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/ed7a021c-fe92-47a6-a23e-0fe99c6fc955)



- **update the apt peckage on the mysql client**
  
 ```
 apt update -y
  ```

![apt update for client](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/dec8c9cf-af14-4b62-a38b-55ec176404cd)

- **On mysql client Linux Server install MySQL Client software**

```
apt install mysql-client
```
  

![install mysql client](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/c29441b0-72eb-44bc-8242-6aa67d972316)

- **From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH**

```
  mysql -u remote_user -h 172.31.24.218 -p
```


![connect to the mysql server from the mysql client](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/050528f6-0338-4409-9c60-c43cfa73bb94)



-  **Checking that i have successfully connected to a remote MySQL server and i can perform SQL queries:**

```
show databases;
```


![use show databases to check if we now connected to the sql server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/1a660e24-9279-48db-9043-423a00a7e150)

- **I have deployed a fully functional MySQL Client-Server**
