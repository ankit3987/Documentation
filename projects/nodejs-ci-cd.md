Live DevOps Project for Resume - Jenkins CICD with GitHub Integration (Notes)

Configure jenkins and docker then deploy project using jenkins

github --> docker --> jenkins --> aws

Create AWS EC2 instance

Install java:-
        sudo apt update
        sudo apt install openjdk-11-jre
        java -version
  

Install jenkins:-
        curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \   /usr/share/keyrings/jenkins-keyring.asc > /dev/null 
        echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \   https://pkg.jenkins.io/debian binary/ | sudo tee \   /etc/apt/sources.list.d/jenkins.list > /dev/null
            sudo apt-get update 
            sudo apt-get install jenkins
            sudo systemctl enable jenkins
            sudo systemctl start jenkins
            sudo systemctl status jenkins
        sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    
Install docker:-
        sudo apt install docker.io
            
            In the docker file:-
                FROM node:12.2.0-alpine
                WORKDIR app
                COPY . .
                RUN npm install
                EXPOSE 8000
                CMD ["node","app.js"]


    
    docker build . -t node-app
    sudo usermod -a -G docker $USER
    docker run -d --name node-todo-app -p 8000:8000 todo-node-app
 
Got to jenkins job
    Execute shell:- 
        docker build . -t node-app-todo
        docker run -d --name node-app-container -p 8000:8000 node-app-todo

this is the video where i learn to make this fucking project:-
https://www.youtube.com/watch?v=nplH3BzKHPk&list=PLlfy9GnSVerRqYJgVYO0UiExj5byjrW8u&index=15
    * coolify
