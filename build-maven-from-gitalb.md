1. In scm paste git repo url and give credential if private 

2. choose pool scm for checking every minut in the git repo and if some changes ocure then it will automatically build the job

3. delete workspace

4. making war file :- 
    build step :invoke top level maven target 
    goal:-clean compile package 
    this line will delete the exixting folder and compile the source ocde and then package it in war file

5. deploy war file to _________(plugin deploy war)
    **/*.war
    
