Pre-requisite
*   account on aws 

# [Application deploy on EBS](https://aws.amazon.com/ebs/?nc2=type_a)

## Click on the create application 
![.](ss-for-ebs/1.png)
###       1.Write the name of the application you want ![.](ss-for-ebs/2.png) 
###       2.Choose plateform(java) ![.](ss-for-ebs/3.png)  
            1.Click sample application for testing purpose if you dont have your own 
![.](ss-for-ebs/4(1).png) 
            2.Upload your code 
![.](ss-for-ebs/4(2).png) 
###       3.Click on local file and select the jar file form the system ![.](ss-for-ebs/4(2).png) 
            Click next
###       4.If you are first time using then click on create and use new service role ![.](ss-for-ebs/6.png) 
            Click on next
###       5.Select VPC(virtual private cloud) ![.](ss-for-ebs/7.png) 
###       6.Under instance settings 
            Check activate the public ip address
###       7.Select all the availabilty zone(optional)
            Click next
###       8.Set environment properties and enter the SERVER_PORT = 5000(default port) ![.](ss-for-ebs/8.png) 
            Then review form and submit it
###       9.Click dashboard of application and click on the dns url ![.](ss-for-ebs/9.png) ![.](ss-for-ebs/9-1.png) 

*Note: After using services make sure you stop that service*