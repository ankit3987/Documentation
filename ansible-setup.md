Ansible :- It is use to manage all the server in the single master node.It is use for control the multiple server 

sudo apt update
sudo apt install ansible
pwd
cd .ssh/
vim ansible_key :- paste pem key in this area



mkdir ansible
cd ansible/
nano hosts :-  
    [servers]
    server1 ansible_host = 3.109.185.251
    server2 ansible_host = 13.126.195.24
    server3 ansible_host = 13.234.110.190


check inventary file (host file is correct or not ) :- 'ansible-inventory --list -y -i /home/ubuntu/ansible/hosts'

change permisions :-
chmod 700 ~/.ssh
chmod 600 ~/.ssh/ansible_key

To check the connection on all the server in one command :-
ansible all -m ping -i /home/ubuntu/ansible/hosts --private-key=~/.ssh/ansible_key

To check the free disk space on all the server in one command :-
ansible all -a "free -h" -i /home/ubuntu/ansible/hosts --private-key=~/.ssh/ansible_key

To check the disk space on all the server in one command :-
ansible all -a "df -h" -i /home/ubuntu/ansible/hosts --private-key=~/.ssh/ansible_key

To check the uptime on all the server in one command :-
ansible all -a "uptime" -i /home/ubuntu/ansible/hosts --private-key=~/.ssh/ansible_key

next step is in the project folder(by ansible project)
what i m doing is that i m building or making a playbook and run on all the server connected to the master node