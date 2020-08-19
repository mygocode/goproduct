# Test Driven Development with GO
The purpose of this appication is to learn and implement Test Driven Development with Golang. 
We have 4 files
- main.go
- app.go
- model.go
- main_test.go

# What the go files are doing  

```main.go``` creates an object of App Struct and performs the initialization of environment variables. If you are using Linux then you can create the environment variables with following command

```shell
$ export APP_DB_PASSWORD=[your password]
$ export APP_DB_USERNAME=postgres
$ export APP_DB_NAME=postgres 
```
![Linux-Environment-variables](https://i.ibb.co/TYdYFpb/Screenshot-env-var.png)

```model.go``` contains the *Product Struct* and CURD methods. CRUD method contains databsae queries related to the methods.
```app.go``` this file is the heart of the application where all the wiring is present. 
> - ```main.go``` calls the initialize method by passing 3 parameters and then calls ```run()``` 
> - ``` Initialize()``` sets the database connection and configure the routes by calling ```InitializeRoutes()``` 

```main_test.go```  this file contains all the test which will test the CURD functionality. 

# API Specification
    
- To Create a valid ```POST``` request = **/product**
- To Update a valid ```PUT``` request = **/product/{id}**
- To Delete a valid ```DELETE``` request = **/product/{id}**
- To Fetch single product with a valid ```GET``` request = **/product/{id}**
- To Fetch a list of products with a valid ```GET``` request = **/products**
    
# Where is Database and how it is configured

Postgres database is used for this demo app and it is a Docker container. 
You will have to install Docker in you dont have it on your machine.
To download and run the postgres docker instance, you can use the following command
```shell
$ sudo docker run -it -e POSTGRES_PASSWORD=[your password] -p 5432:5432 -d postgres
```
Check the postgres instance using following command
```shell
$ sudo docker ps
```

# How to run the application
There is no graphical interface of this application. To run the application you will have to run the test file.
Run the test file and get the understang of the code flow. 
To run, type the following command
```shell 
$ go test -v 
```

![Test Result](https://i.ibb.co/jD2LxCG/Go-Test-Result.png)

For detailed understanding please refer to the this link
https://semaphoreci.com/community/tutorials/building-and-testing-a-rest-api-in-go-with-gorilla-mux-and-postgresql

Happy coding with GO! :herb:
