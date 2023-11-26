# Implementing a Client Server Architecture using MySQL Database Management System (DBMS)


![client-server](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/12d002f3-b7ca-4cef-9ac3-ad26af45ed2d)


- **Created 2 ec2 instances that is mysql client and mysql server**


![new ec2 instances created](https://github.com/titusnangitech/Client-Server-architecture-implemantation-using-MySql/assets/128609800/c562a1b0-4de2-4597-82ab-2eef6b6a3187)


- **MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your ‘mysql client’.**


- **Connect to the 2 instances using Mobaxterm and swictched to root user**

- **update the apt peckage for the server**
  
 ```
  apt update -y
  ```

 - **Install mysql-server**
 ```
apt install mysql-server

```

- **Enable mysql**

```
systemctl enable mysql
```



- **On mysql server Linux Server install MySQL Server software.**

  

- **On mysql client Linux Server install MySQL Client software.**
