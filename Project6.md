### WEB SOLUTION WITH WORDPRESS.
##LAUNCH AN EC2 INSTANCE THAT WILL SERVE AS “WEB SERVER”
I launch an ec2 instance. i Used lsblk command to inspect what block devices are attached to the server
![image](https://user-images.githubusercontent.com/103155174/170602872-738149fc-00a3-493f-8ad0-51d6185ca666.png)
![image](https://user-images.githubusercontent.com/103155174/170602825-2d6103f5-d4a4-49c3-bd00-906a5ad8e540.png)
![image](https://user-images.githubusercontent.com/103155174/170603001-4a32410a-c4f2-44e2-9313-1255b37ab2f0.png)
Verify that your Physical volume has been created successfully by running
Verify that your Logical Volume has been created successfully by running
Verify the entire setup
![image](https://user-images.githubusercontent.com/103155174/170604916-62707642-eb4f-4b20-a4f5-d2edf56c9683.png)
Use mkfs.ext4 to format the logical volumes with ext4 filesystem
![image](https://user-images.githubusercontent.com/103155174/170605072-db967a72-2f93-47ff-9e33-dc33f66cd928.png)
![image](https://user-images.githubusercontent.com/103155174/170605826-6bc24234-6273-45bc-8db4-436a277774fc.png)
![image](https://user-images.githubusercontent.com/103155174/170606229-92e9b050-1ce8-4835-87ff-a95791fcb242.png)
## UPDATE THE `/ETC/FSTAB` FILE
![image](https://user-images.githubusercontent.com/103155174/170609821-7095e574-8e92-4e79-ad1a-02e8751a4a50.png)
