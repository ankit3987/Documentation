
### Install java:

`sudo apt update`
`sudo apt install default-jdk -y`

### Install pm2:

`curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -`
`sudo apt install -y nodejs`
`sudo npm install -g pm2`


**version :** 
`pm2 -v` 


**Start the new application:**
`pm2 start "java -jar your-app.jar" --name your-app-name`
or 
`pm2 start --name kmp.sh`


### Manage the Application with PM2
1) Check status: 
`pm2 status`
`pm2 list`


2) Stop the application: 
`pm2 stop your-app-name`

3) Restart the application:
`pm2 restart your-app-name`

4) View logs: 
`pm2 logs your-app-name`
