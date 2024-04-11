# 3 Tier Architecture Mini Project Important Notes and Tips.

As per the readme files for frontend, backend and MysqlDB, create the instances and configure them.
so you will face an issue when you enter below command in backend as it won't complete or connect with backend server.

```
mysql -h 172.31.45.116 -uroot -pExpenseApp@1 < /app/schema/backend.sql
```
then add the 3306 port in outboud rules of the security group which we assigned to EC2 instances.
and then start the backend service in backend server, so you will be able to connect to database with below command from backend server.
```
mysql -h 172.31.45.116 -uroot -pExpenseApp@1
```
below are useful commands to enter in mysql DB:
```
show databases;
```
```
use transactions;
```
```
show tables
select * from transactions;
```
Here you will see all the expense detais we give in the GUI once we connect to application from browser via frontend server public IP address.

Then now in frontend server after installing nginx and all, you will face an issue while connecting to it from browser and the default page will not showup. It because we didn't allowed port 80 in outboud/inboud rules.
So allow the same.
After downloading the application and unzipping it, if you try to connect again from browser, It won't connect. So then check the services from all the servers.
frontend: nginx should be running
backend: backend service should be running
Mysql-DB: mysqld service should be in running state.
Also if you till face any issues, check if you have allowed 3306,80,8080, 22 port to anywhere in security Groups.
If any of the above service is in failed state, application won't be able to connect.

 ++++++++++++++++ END ++++++++++++++++++
"
