![image](https://user-images.githubusercontent.com/55301074/219312228-c049a5a7-ad38-4035-98bc-d406af904657.png)

## Install library

    cd database
    mvn clean install
    
## Run

    docker-compose up 
    
# Data import microservice REST API

## Import Employee Profiles

* **URL:**
    
    `/api/upload/importEmployeeProfiles`

* **Method**

    `POST`

* **URL Params:**

    None

* **Body Params:**
    
    File content: `employee_profiles.csv`

* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "message": "Import successful." }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": "Import successful." }`

## Import Used Vacations

* **URL:**
    
    `/api/upload/importUsedVacations`

* **Method**

    `POST`
    
* **URL Params:**

    None

* **Body Params:**
   
    File content: `used_vacation_dates.csv`
    
* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "message": "Import successful." }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": "Import successful." }`
    
## Import Available Vacation Days Per Year

* **URL:**
    
    `/api/upload/importAvailableVacationDaysPerYear`

* **Method**

    `POST`
    
* **URL Params:**

    None

* **Body Params:**
    
    File content: `vacations_2019.csv`

* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "message": "Import successful." }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": "Import successful." }`
    
## Clear Database

### Request

* **URL:**
    
    `/api/upload/clearDatabase`

* **Method**

    `POST`
    
* **URL Params:**

    None

* **Body Params:**

    None
    
* **Success response:**

    * **Code**: 200
    
    * **Content**: None
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": "Import successful." }`
    
# Data search microservice REST API

## Get Vacation Days Per Year

* **URL:**
    
    `/api/search/getVacationDaysPerYear?year=targetYear`

* **Method**

    `GET`
    
* **URL Params:**

    **Required**
    
    `year=[date]`
    
    **Optional**
    
    None

* **Body Params:**

    None

* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "totalDays": 20, "usedDays": 12, "availableDays": 8 }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": "Import successful." }`

## Get Used Vacation Days For Time Period

* **URL:**
    
    `/api/search/getUsedVacationDaysForTimePeriod?startDate=targetStartDate&endDate=targetEndDate`

* **Method**

    `GET`
    
* **URL Params:**

    **Required**
    
    `startDate=[date]`
    
    `endDate=[date]`
    
    **Optional**
    
    None

* **Body Params:**

    None

### Response

* **Success response:**

    * **Code**: 200
    
    * **Content**: 
    `[
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
    ]`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": "Import successful." }`

## Insert New Record

* **URL:**
    
    `/api/search/insertNewRecord`

* **Method**

    `POST`

* **URL Params:**

    None

* **Body Params:**

        {
            "startDate": 2019-08-30,
            "endDate": 2019-09-01
        }
    
* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "message": "New vacation ID: 640" }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": "New vacation ID: 640" }`
