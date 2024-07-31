if u want tomcat and jenkins on same server then change the default port on tomcat

1. [then go to tomcat offical website](https://tomcat.apache.org/download-10.cgi) 
        then copy the core url .tar.gz


2. wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.26/bin/apache-tomcat-10.1.26.tar.gz

3. tar xvzf apache-tomcat-10.1.26.tar.gz
this is for extract the tar file

4. rm apache-tomcat-10.1.26.tar.gz
this is for remove the tar fir

5. mv apache-tomcat-10.1.26.tar.gz/ tomcat 
this is for rename the file 

6. change the default port from the server.xml and change the user from user.xml in conf directory

7. /bin -> sh startup.sh
this is for start or shutdown the tomcat

open the port 5050 in the vm machine


another method is :- sudo apt install tomcat10


webapps:- /var/lib/tomcat10
install tomcat on :- /etc/tomcat10

to acces the admin: -sudo apt install tomcat10-admin


possible errors : 403 acces denied :- https://askubuntu.com/questions/1147402/403-with-tomcat-manager






after downloading all the file of tomcat then add user make admin username and password