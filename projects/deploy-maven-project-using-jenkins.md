deploy manually 

unit test
code quality check ->
build 
deploy on testing environment
deploy on staging environment
deploy on production environment

In manually:-
unit test -> build -> deploy on test -> deploy on prod

clone your code from github and then install maven in your computer 'sudo apt install maven'
then write 
    -mvn test :- to test the file 
    then write - mvn install :- to make build or war file 