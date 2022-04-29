## WEB STACK IMPLEMENTATION (LEMP STACK)
I Downloaded and install Git Bash.
Launch Git Bash and run following command: ssh -i "PBLdevops.pem" ubuntu@ec2-54-198-152-241.compute-1.amazonaws.com
![image](https://user-images.githubusercontent.com/103155174/165951956-380b77b2-ccb2-4e69-9142-133fe627ed38.png)
# STEP 1 – INSTALLING THE NGINX WEB SERVER
I undated my server using command sudo apt update
![image](https://user-images.githubusercontent.com/103155174/165952670-70dfb8e9-90e9-488a-9e36-8ea83cd53af6.png)
The next step is to intsall Nginx. sudo apt install nginx
![image](https://user-images.githubusercontent.com/103155174/165953320-4e0bc38d-2d2f-436f-8535-e8ad0e6c443c.png)
To make sure that nginx was successfully installed and is running as a server in Ubuntu. i ran the command: sudo systemctl status nginx
![image](https://user-images.githubusercontent.com/103155174/165953719-11756a32-36fd-407b-9fbe-244016bccc1d.png)
I ran the command curl http://localhost:80let to check locally in Ubuntu shell. 
![image](https://user-images.githubusercontent.com/103155174/165955073-b96cfacf-30cd-44e5-b7de-365e0e116cb3.png)
i tested my Nginx server to see if it can respond to the internet rquests. i copied and paste my ip address :54.198.152.241
![image](https://user-images.githubusercontent.com/103155174/165957054-50ddc1fd-4cbc-4ae0-b4c1-dafaca143da8.png)
![image](https://user-images.githubusercontent.com/103155174/165957272-0a913195-5915-400a-a9d3-38ab8d492e58.png)
# STEP 2 — INSTALLING MYSQL.
To install MYSQL. i used the command: sudo apt install mysql-server
![image](https://user-images.githubusercontent.com/103155174/165957775-f4c71840-0c2c-457c-86b4-0d12e599a3d7.png)
 Start the interactive script by running: sudo mysql_secure_installation
 ![image](https://user-images.githubusercontent.com/103155174/165958241-cc89657d-eda1-4ba4-bd0f-edfdcd309f22.png)
When you’re finished, test if you’re able to log in to the MySQL console by typing:sudo mysql
![image](https://user-images.githubusercontent.com/103155174/165958492-90f87085-003f-4d2a-be8c-070133040ed1.png)
# STEP 3 – INSTALLING PHP
To install these 2 packages at once, run:sudo apt install php-fpm php-mysql
![image](https://user-images.githubusercontent.com/103155174/165960795-42bb6699-a988-406a-9b55-ec0e4f41ce32.png)
# Step 4 — Configuring Nginx to Use PHP Processor
To create the root web web directory for your_demain : sudo mkdir /var/www/projectLEMP
assign ownership of the directory with the $USER environment variable, which will reference your current system user:sudo chown -R $USER:$USER /var/www/projectLEMP
![image](https://user-images.githubusercontent.com/103155174/165962597-45e40532-d1d4-487a-a2b9-bd7056b3b6fd.png)
open a new configuration file in Nginx’s sites-available directory using your preferred command-line editor. Here, we’ll use nano:sudo nano /etc/nginx/sites-available/projectLEMP
![image](https://user-images.githubusercontent.com/103155174/165962783-5e9d51a7-9277-4f8d-b64e-c9a3af1fc84e.png)
create a new blank file. Paste in the following bare-bones configuration
![image](https://user-images.githubusercontent.com/103155174/165965728-4f7cb48d-8844-43e4-a096-95d94bdf69f9.png)
Activate your configuration by linking to the config file from Nginx’s sites-enabled directory:sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/
![image](https://user-images.githubusercontent.com/103155174/165966124-22beefeb-6f5f-48e5-99ee-f45490ecc016.png)
need to disable default Nginx host that is currently configured to listen on port 80, for this run
 reload Nginx to apply the changes:
![image](https://user-images.githubusercontent.com/103155174/165966710-07820fea-755a-42ab-a03e-0515ec6e21f4.png)
![image](https://user-images.githubusercontent.com/103155174/165967016-7799d01b-0115-44df-967f-2009d89e44ab.png)
# STEP 5 – TESTING PHP WITH NGINX
Type or paste the following lines into the new file. This is valid PHP code that will return information about your server 
<?php
phpinfo();
![image](https://user-images.githubusercontent.com/103155174/165969234-e041a23c-5714-4c4b-9164-17ee835a4144.png)
![image](https://user-images.githubusercontent.com/103155174/165970035-2338eb68-5cd0-40c2-80ee-6efb5849bce5.png)
# STEP 6 – RETRIEVING DATA FROM MYSQL DATABASE WITH PHP (CONTINUED)
First, connect to the MySQL console using the root account:
![image](https://user-images.githubusercontent.com/103155174/165970471-9db5dff7-2484-45ca-829c-ee40684b6569.png)
![image](https://user-images.githubusercontent.com/103155174/165973527-104bc1c5-a930-4821-8724-1569b1ad7327.png)
Now we need to give this user permission over the example_database database:
![image](https://user-images.githubusercontent.com/103155174/165973744-bc39b815-ae62-43d3-92bd-2a03a270f0d4.png)
logging in to the MySQL console again, this time using the custom user credentials:
![image](https://user-images.githubusercontent.com/103155174/165974126-03294e54-382f-437e-a628-69418537a58a.png)
confirm that you have access to the example_database database:mysql> SHOW DATABASES;
![image](https://user-images.githubusercontent.com/103155174/165974325-031185cd-4d05-4665-b7fe-6c72b05fc5d0.png)
create a test table named todo_list. From the MySQL console, run the following statement:
CREATE TABLE example_database.todo_list (
mysql>     item_id INT AUTO_INCREMENT,
mysql>     content VARCHAR(255),
mysql>     PRIMARY KEY(item_id)
mysql> );
![image](https://user-images.githubusercontent.com/103155174/165975143-3c5c6461-2edf-432f-85a7-1647301de32d.png)
Insert a few rows of content in the test table
![image](https://user-images.githubusercontent.com/103155174/165975415-ec71199a-d6da-46e6-9777-7f25ee11473f.png)
To confirm that the data was successfully saved to your table, run:
![image](https://user-images.githubusercontent.com/103155174/165976188-2c63d47c-f90f-4aa1-ae07-37e438336157.png)
![image](https://user-images.githubusercontent.com/103155174/165976339-0063850f-3183-44e1-8bac-48ea7a586691.png)
mysql>  SELECT * FROM example_database.todo_list;
![image](https://user-images.githubusercontent.com/103155174/165976903-f7138ff9-55a6-412c-8122-4455e423e667.png)
 create a PHP script that will connect to MySQL and query for your content. Create a new PHP file in your custom web root directory using your preferred editor. We’ll use vi for that:
![image](https://user-images.githubusercontent.com/103155174/165977405-14cd288f-6f79-4cc3-8bc8-50183e0e4aae.png)

