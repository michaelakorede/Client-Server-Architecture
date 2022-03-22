
Your terminal will be the client, while www.propitixhomes.com will be the server.

See the response from the remote server in below output. You can also see that the requests from the URL are being served by a computer with an IP address 160.153.133.153 on port 80. 

 curl -Iv www.propitixhomes.com

 ![](2022-03-22-09-16-32.png)

### IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).

1. Create and configure two Linux-based virtual servers (EC2 instances in AWS).

Server A name - `mysql server`

Server B name - `mysql client`

>On mysql server Linux Server install MySQL Server software

>On mysql client Linux Server install MySQL Client software

![](2022-03-22-09-32-19.png)

![](2022-03-22-09-34-28.png)

2. By default, both of your EC2 virtual servers are located in the same local virtual network, so they can communicate to each other using local IP addresses. Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups.
   
![](2022-03-22-09-29-51.png)

3. You might need to configure MySQL server to allow connections from remote hosts.

>sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf
Replace ‘127.0.0.1’ to ‘0.0.0.0’ like this:

![](2022-03-22-09-30-52.png)

4. From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.

5. Check that you have successfully connected to a remote MySQL server and can perform SQL queries:

Show databases;

![](2022-03-22-09-32-58.png)