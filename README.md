# Openid Connect Authorization Server

## What is this? 

This is an open id connect authorization server using the orchard cms project and openiddict module for authorization.

## How is this configured?
https://kevinchalet.com/2020/10/03/using-the-orchardcore-openid-management-feature-with-an-existing-openiddict-deployment/

## How is this run? 

### Dependencies 
#### SQL Server
Run an instance of SQL Server on the dev machine or using a container. Use the below files if the authorization server 
will be run on the local machine without a container 

To run SQL Server in a container, use one of the following docker-compose files
- docker-compose-sql.yml for running in windows or mac
- docker-compose-sql-arm.yml for running in mac m1 or any other arm based servers

#### .NET Core
Install and run dotnet core 3.1 or higher. 
- https://dotnet.microsoft.com/download/dotnet-core/3.1

### Running the server
To run authorization server in a container, use the following docker compose file
- docker-compose.yml  runs the authorization server and sql server container 
- docker-compose-no-db.yml runs only the authorization server
- docker-compose-arm-db.yml runs the authorization server and arm based sql server



