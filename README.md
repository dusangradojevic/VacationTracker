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

    curl -i -H 'Accept: application/json' -t 'file=employee_profiles.csv' http://localhost:8081/api/upload/importEmployeeProfiles

### Response

    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 2

    []

## Import Used Vacations

### Request

`POST /api/upload/importUsedVacations`

    curl -i -H 'Accept: application/json' -t 'file=used_vacation_dates.csv' http://localhost:8081/api/upload/importUsedVacations

### Response
    
    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 2

    []

## Import Available Vacation Days Per Year

### Request

`POST /api/upload/importAvailableVacationDaysPerYear`

    curl -i -H 'Accept: application/json' -t 'file=vacations_2019.csv' http://localhost:8081/api/upload/importAvailableVacationDaysPerYear

### Response

    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 2

    []

## Get Vacation Days Per Year

### Request

`GET /api/search/getVacationDaysPerYear?year=targetYear`

    curl -i -H 'Accept: application/json' http://localhost:8080/api/upload/getVacationDaysPerYear?year=2019

### Response

    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 2

    []

## Get Used Vacation Days For Time Period

### Request

`GET /api/search/getUsedVacationDaysForTimePeriod?startDate=targetStartDate&endDate=targetEndDate`

    curl -i -H 'Accept: application/json' http://localhost:8080/api/search/getUsedVacationDaysForTimePeriod?startDate=2019-09-30&endDate=2019-10-30

### Response

    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 2

    []

## Insert New Record

### Request

`POST /api/search/insertNewRecord`

    curl -i -H 'Accept: application/json' -d 'startDate=2019-08-30&endDate=2019-09-01' http://localhost:8080/api/search/insertNewRecord

### Response

    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 2

    []

## Clear Database

### Request

`POST /api/upload/clearDatabase`

    curl -i -H 'Accept: application/json' http://localhost:8081/api/upload/clearDatabase

### Response

    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 2

    []
