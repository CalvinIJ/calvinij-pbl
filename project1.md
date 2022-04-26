## WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS
# STEP 1 — INSTALLING APACHE AND UPDATING THE FIREWALL
Apache, i installed Apache using Ubuntu's manager 'apt' with the command sudo apt update
![image](https://user-images.githubusercontent.com/103155174/165203087-7976d3f4-b63b-4248-adf3-b3ed2e1a128c.png)
#run apache2 package installation, i used command sudo apt install apache2
![image](https://user-images.githubusercontent.com/103155174/165203423-df2d9764-ddd2-4476-9554-3a4f00ebd7fb.png)
Yes to continue.
![image](https://user-images.githubusercontent.com/103155174/165203665-bd900b6a-c887-40e2-8beb-c49e96e8fbaf.png)
To verify that apache2 is running as a Service in our OS, use following command, i used sudo systemctl status apache2
![image](https://user-images.githubusercontent.com/103155174/165203935-e03b30ea-02d0-4166-95e4-8649db635707.png)
its running and active.
Before we can receive any traffic by our Web Server, we need to open TCP port 80 which is the default port that web browsers use to access web pages on the Internet
i ckecked how we can access it locally. i used the command  curl http://localhost:80
![image](https://user-images.githubusercontent.com/103155174/165204387-3cb5cd90-2650-4319-85bd-68ad176dbed4.png)
![image](https://user-images.githubusercontent.com/103155174/165204471-13eccca4-9539-4255-b162-55a6c6b4da99.png)
# STEP 2 — INSTALLING MYSQL
i used command sudo apt install mysql-server to install MYSQL
![image](https://user-images.githubusercontent.com/103155174/165204874-68bbf829-612a-4633-a447-a00fea1adb0c.png)
![image](https://user-images.githubusercontent.com/103155174/165205082-31ed425a-c654-4b3f-be6c-7947b3559640.png)
I started the intreactive by running sudo mysql_secure_installation
![image](https://user-images.githubusercontent.com/103155174/165205551-686d6cd1-5d46-417c-a2fe-efb54354e95c.png)
When you’re finished, test if you’re able to log in to the MySQL console by typing: sudo mysql
![image](https://user-images.githubusercontent.com/103155174/165206017-67410085-02a3-45db-ba38-9767b005343e.png)
 # STEP 3 — INSTALLING PHP
 to installed 3 packages at once. sudo apt install php libapache2-mod-php php-mysql
 ![image](https://user-images.githubusercontent.com/103155174/165206981-56094c22-04bb-4885-9086-5e65440c85cd.png)
![image](https://user-images.githubusercontent.com/103155174/165207116-3e252e25-cd42-4f6b-979c-31f30e75effe.png)
after the installation.  php-v to confirm
![image](https://user-images.githubusercontent.com/103155174/165207374-87d4d667-c32e-41bd-9c79-1e202cd712d7.png)
#STEP 4 — CREATING A VIRTUAL HOST FOR YOUR WEBSITE USING APACHE
Create the directory for projectlamp using ‘mkdir’ command as follows: sudo mkdir /var/www/projectlamp
![image](https://user-images.githubusercontent.com/103155174/165207721-8d955128-6774-4dbc-a1af-9f6a1b9404e2.png)
assign ownership of the directory with your current system user: sudo chown -R $USER:$USER /var/www/projectlamp
![image](https://user-images.githubusercontent.com/103155174/165208122-c6408093-d70c-4423-b146-fa45c564a0ae.png)
![image](https://user-images.githubusercontent.com/103155174/165208342-edef7b52-6d7c-49a0-b537-9e77c3694b42.png)
You can now use a2ensite command to enable the new virtual host:
i disable the website
![image](https://user-images.githubusercontent.com/103155174/165208737-8d93a6a5-0f5f-4e80-ae0a-310391b781a3.png)
![image](https://user-images.githubusercontent.com/103155174/165209231-938bdaca-5c89-472d-948e-b84a3be61723.png)

Your new website is now active, but the web root /var/www/projectlamp is still empty. Create an index.html file in that location so that we can test that the virtual host works as expected:
#STEP 5 — ENABLE PHP ON THE WEBSITE
Create a new file named index.php inside your custom web root folder
![image](https://user-images.githubusercontent.com/103155174/165211556-8000f151-e955-42a1-abae-662d9f2ec1d6.png)
![image](https://user-images.githubusercontent.com/103155174/165211693-b303e410-5cc8-410c-bd16-63987de765a7.png)



