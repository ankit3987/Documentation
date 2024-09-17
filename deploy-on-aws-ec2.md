# Application deploy on EC2 instance
##  Search EC2 in the aws dashboard

###       Create instance (virtual machine) 

####      Click on launch instance ![.](ss-for-ec2/1.png) 

*            Write the name of your instance 
![.](ss-for-ec2/2.png)
*            Select OS
![.](ss-for-ec2/3.png)
*            Select instance type (t2 micro is free tier) 
 ![.](ss-for-ec2/4.png)
*            Select key pair to access the instance 
![.](ss-for-ec2/4.1.png) 
                    If not created then create fresh one by clicking create new key
                        Enter the name of key 
                        And click on the create key
*            In the network setting open https and http port by checking the box
![.](ss-for-ec2/5.png)  
*            Click the launch instance

###     Click on the instance id and click on the connect ![.](ss-for-ec2/7.png) 
![.](ss-for-ec2/7.1.png) 
            Then there are several ways to access the instance 
                    1. EC2 instance connect
![.](ss-for-ec2/7.1.1.png)  

                        Click on the connect 
![.](ss-for-ec2/7.1.1.1.png) 
                    2. SSH client 
![.](ss-for-ec2/7.1.2.png) 
                        Copy the ssh command and open window terminal go to that directory where your key-pair.pem key present and paste it on the terminal
![.](ss-for-ec2/7.2.png) 
###     Create a fresh folder for the project(spring-boot) in the ubuntu machine 
![.](ss-for-ec2/8.png) 
            now your jar file copy under that folder from your local machine to remote machine by command 

###    Write this cmd on your local machine
![.](ss-for-ec2/9.png) 
            `scp -i location/of/your-key-pair-file source(file-to-transfer) detination(username@ip:location)`
            eg- `scp -i download/ankit-key.pem c:Dekstop/abc.jar ubuntu@12.143.124.12:/home/ubuntu/spring-boot`

###     Open your ubuntu machine and check jar file is there or not if yes  
![.](ss-for-ec2/10.png) 
            then run your jar file from that location by cammand "java -jar abc.jar"
![.](ss-for-ec2/11.png) 

###     Copy the public ip of remote machine and paste it on the browser 
![.](ss-for-ec2/12.png) 

            "112.124.54.64:8080"
![.](ss-for-ec2/13.png) 


*Note: After using services make sure you stop that service*