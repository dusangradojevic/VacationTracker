![image](https://user-images.githubusercontent.com/55301074/219312228-c049a5a7-ad38-4035-98bc-d406af904657.png)

## Install library

    cd database
    mvn clean install
    
## Run

    docker-compose up 
    
# REST API

The REST API is described below.

## Import Employee Profiles

### Request

`POST /api/upload/importEmployeeProfiles`

    curl -i -H 'Accept: application/json' http://localhost:8081/api/upload/importEmployeeProfiles

### Response
