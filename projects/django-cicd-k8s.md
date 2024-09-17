this is end to end project with docker ,docker compose ,jenkins,aws with todo python app


github  ---> docker ---> jenkins ---> aws cloud


1. 1st step :- run code in local machine
        git clone 'repo'
         [optional but recomened]Then u can create virtual env in local
         crete the env 'python -m venv env'
         to activate the environment 'env\Scripts\activate'
        run all the command to run the application present in the readmefile (for e.g 'pip install django','python manage.py migrate','python manage.py crtatesupeuser','python manage.py runserver')
        this will run your project on the local machine 

2. 2nd step :- run this code on server aws
            Everything is same as abov but this cmd change becouse we have to open project from everywhere 'python manage.py runserver 0.0.0.0:8000'
            It will hold the screen while running the application and if u want to run application in background then wrtie 'nohup: python manage.py runserver 0.0.0.0:8000 &'

[Note] :- While doing this i face an error and i fixed it by updating the settings.py file and add the ip of the server and i add '*' in ALLOWED_HOSTS=['*'] or u can add ip of the server in it

3. 3rd step :- now automate the docker then install and setup docker in your server and create the dockerfile in your directory
        - FROM python:3
        - RUN pip install django==3.2
        - COPY . .
        - RUN python manage.py migrate
        - CMD["python","manage.py","runserver","0.0.0.0:8000"]
  
        'sudo docker build . -t todo-app'
        'sudo docker run todo-app -d -p 8000:8000 ' 

4. 4rth step :- setup and install jenkinson the server 
[Optional but intersting] Install jenkins via docker in the container
        'sudo pull jenkins/jenkins'  #this will pull image from dockerhub     
        'sudo docker run -d -p 8888:8080 jenkins/jenkins'   

5. 5th step :- 
   1. This is without git scm and these are the cmd in shell
        'sudo docker build -t todo-app -f /home/ubuntu/project/django-todo/Dockerfile  /home/ubuntu/project/django-todo'
        'sudo docker run -d -it -p 8000:8000 todo-app'

   2. In this CI learning with github push all the code in github 
        - Personal Access Tokens :- create pat in github and copy secrete key 
        - Jenkins and Github integration :- manage jenkins/configure system/github/ add creadential to jenkins with secrete text and paste the pat in the creadentials and then test connection for accurate connection or not
        - CI/CD pipeline :- create free style project then paste github-repos in scm 
            - 'sudo docker build . -t todo-app'
            - 'sudo run -d -p 8000:8000 todo-app'
[Note] after chnaging in github we have to kill or stop the freaking container so in next step we use docker-compose

6. 6th step :- install docker compose
                'sudo apt-get install docker-compose-plugin' 
                'docker compose version'
                nano docker-compose.yml
                  version : 3.3
                  services :
                      web :
                        build : .    #Dockerfile present on the same directory
                        ports : 
                           - 8000:8000
                'sudo docker compose up -d'

7. 7th step :- Now push all the things to the github including docker-compose.yml and now we can automate it fro jenkins without killing the container
                  write execute shell
                        'sudo docker-compose down'
                        #'sudo docker-compose up -d'
                        'sudo docker-compose up -d --force-recreate --no-deps --build web'
                        
All the things done here now we are going to next level deploying with kubernetes

dcoker ---> docker hub ---> kubernetes

8. 8th step :- 

docker build -t ankitrawat3987/todoapp:v1 .
docker images
docker run -it -p 8000:8000 08b6b91ca915
mkdir k8s
cd k8s/
docker images
clear
docker images
  
docker login
docker push ankitrawat3987/todoapp:v1
nano pod.yml
kubectl apply -f pod.yml
kubectl get pods
kubectl get pods -o wide
minikube ssh
        curl -L private-ip:8000

kubectl get pods
kubectl delete pod todo-app
minikube ssh
nano deploy.yml
kubectl apply -f deploy.yml
kubectl get pods
nano deploy.yml
kubectl get pod -o wide
minikube ssh
kubectl get pod -o wide
nano service.yml
kubectl apply -f service.yml
kubectl get svc

minikube service todo-service --url

curl -L 192.168.49.2:30009

and 

if you wnat to acces the website from outside then u can write bellow cmd make sure your port open from aws

kubectl port-forward svc/todo-service 8000:8000 --address 0.0.0.0 &


https://www.youtube.com/watch?v=OJths_RojFA


for linked in project or cv
1. Built kubernetes clustre on AWS from scratch with Minikube 
2. Setup and manged docker containers for django and react Application into kubernetes pods
3. managed Deployment , replication autohealing ,auto scalling for kubernetes cluster.
4. managed netwrok and service with host Ip allocation through proxy on AWS EC2 and ROut53

ACHIEVEMENT:Reduced Downtime by 75% on Production environments