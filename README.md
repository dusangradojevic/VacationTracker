![image](https://user-images.githubusercontent.com/55301074/219312228-c049a5a7-ad38-4035-98bc-d406af904657.png)

## Install library

    cd database
    mvn clean install
    
## Run

    docker-compose up 
    
# Data import microservice REST API

## Import Employee Profiles

### Request

`POST /api/upload/importEmployeeProfiles`

    curl -i -H 'Accept: application/json' -t 'file=employee_profiles.csv' http://localhost:8081/api/upload/importEmployeeProfiles

### Response

    Status: 200 OK
    Content-Type: application/json
    Content: 
    {
        "message": "Import successful."
    }

## Import Used Vacations

### Request

`POST /api/upload/importUsedVacations`

    curl -i -H 'Accept: application/json' -t 'file=used_vacation_dates.csv' http://localhost:8081/api/upload/importUsedVacations

### Response
    
    Status: 200 OK
    Content-Type: application/json
    Content: 
    {
        "message": "Import successful."
    }
    
# Data search microservice REST API

## Import Available Vacation Days Per Year

### Request

`POST /api/upload/importAvailableVacationDaysPerYear`

    curl -i -H 'Accept: application/json' -t 'file=vacations_2019.csv' http://localhost:8081/api/upload/importAvailableVacationDaysPerYear

### Response

    Status: 200 OK
    Content-Type: application/json
    Content: 
    {
        "message": "Import successful."
    }
    
## Clear Database

### Request

`POST /api/upload/clearDatabase`

    curl -i -H 'Accept: application/json' http://localhost:8081/api/upload/clearDatabase

### Response

    Status: 200 OK
    Content-Type: text/plain
    Content: None

## Get Vacation Days Per Year

### Request

`GET /api/search/getVacationDaysPerYear?year=targetYear`

    curl -i -H --user "username:password" 'Accept: application/json' http://localhost:8080/api/upload/getVacationDaysPerYear?year=2019

### Response

    Status: 200 OK
    Content-Type: application/json
    Content:
    {
        "totalDays": 20,
        "usedDays": 12,
        "availableDays": 8
    }

## Get Used Vacation Days For Time Period

### Request

`GET /api/search/getUsedVacationDaysForTimePeriod?startDate=targetStartDate&endDate=targetEndDate`

    curl -i -H --user "username:password" 'Accept: application/json' http://localhost:8080/api/search/getUsedVacationDaysForTimePeriod?startDate=2019-09-30&endDate=2019-10-30

### Response

    Status: 200 OK
    Content-Type: application/json
    Content:
    [
        {
            "id": 115,
            "startDate": "2019-10-07T00:00:00.000+00:00",
            "endDate": "2019-10-07T00:00:00.000+00:00"
        },
        {
            "id": 207,
            "startDate": "2019-10-02T00:00:00.000+00:00",
            "endDate": "2019-10-04T00:00:00.000+00:00"
        },
        {
            "id": 520,
            "startDate": "2019-10-01T00:00:00.000+00:00",
            "endDate": "2019-10-07T00:00:00.000+00:00"
        },
    ]

## Insert New Record

### Request

`POST /api/search/insertNewRecord`

    curl -i -H --user "username:password" 'Accept: application/json' -d 'startDate=2019-08-30&endDate=2019-09-01' http://localhost:8080/api/search/insertNewRecord

### Response

    Status: 200 OK
    Content-Type: application/json
    Content:
    {
        "message": "New vacation ID: 640"
    }
