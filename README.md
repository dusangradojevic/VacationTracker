![image](https://user-images.githubusercontent.com/55301074/219312228-c049a5a7-ad38-4035-98bc-d406af904657.png)

## Example files

Example .csv files are located in `files` directory.

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

    **Required:**
    
    `file=[multipart file]`
    
    Example: `employee_profiles.csv`
    
    **Optional:**
    
    None

* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "message": "Import successful." }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": ERROR_MESSAGE, "status": 400, "statusText": "Bad request" }`

## Import Used Vacations

* **URL:**
    
    `/api/upload/importUsedVacations`

* **Method**

    `POST`
    
* **URL Params:**

    None

* **Body Params:**

    **Required:**
    
    `file=[multipart file]`
    
    Example: `used_vacation_dates.csv`
    
    **Optional:**
    
    None
    
* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "message": "Import successful." }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": ERROR_MESSAGE, "status": 400, "statusText": "Bad request" }`
    
## Import Available Vacation Days Per Year

* **URL:**
    
    `/api/upload/importAvailableVacationDaysPerYear`

* **Method**

    `POST`
    
* **URL Params:**

    None

* **Body Params:**

    **Required:**
    
    `file=[multipart file]`
    
    Example: `vacations_2019.csv`
    
    **Optional:**
    
    None

* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "message": "Import successful." }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": ERROR_MESSAGE, "status": 400, "statusText": "Bad request" }`
    
## Clear Database

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
    
    * **Content**: `{ "message": ERROR_MESSAGE, "status": 400, "statusText": "Bad request" }`
    
# Data search microservice REST API

## Get Vacation Days Per Year

* **URL:**
    
    `/api/search/getVacationDaysPerYear?year=targetYear`

* **Method**

    `GET`
    
* **URL Params:**

    **Required:**
    
    `year=[date(YYYY-MMM-dd)]`
    
    **Optional:**
    
    None

* **Body Params:**

    None

* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "totalDays": 20, "usedDays": 12, "availableDays": 8 }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": ERROR_MESSAGE, "status": 400, "statusText": "Bad request" }`

## Get Used Vacation Days For Time Period

* **URL:**
    
    `/api/search/getUsedVacationDaysForTimePeriod?startDate=targetStartDate&endDate=targetEndDate`

* **Method**

    `GET`
    
* **URL Params:**

    **Required:**
    
    `startDate=[date(YYYY-MMM-dd)]`
    
    `endDate=[date(YYYY-MMM-dd)]`
    
    **Optional:**
    
    None

* **Body Params:**

    None

### Response

* **Success response:**

    * **Code**: 200
    
    * **Content**: 

            [
                {
                    "id": 115,
                    "startDate": "2019-10-07",
                    "endDate": "2019-10-07"
                },
                {
                    "id": 207,
                    "startDate": "2019-10-02",
                    "endDate": "2019-10-04"
                },
                {
                    "id": 520,
                    "startDate": "2019-10-01",
                    "endDate": "2019-10-07"
                },
            ]
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": ERROR_MESSAGE, "status": 400, "statusText": "Bad request" }`

## Insert New Record

* **URL:**
    
    `/api/search/insertNewRecord`

* **Method**

    `POST`

* **URL Params:**

    None

* **Body Params:**

    **Required:**

    `startDate=[date(YYYY-MMM-dd)]`
    
    `endDate=[date(YYYY-MMM-dd)]`
    
    **Optional:**
    
    None
    
* **Success response:**

    * **Code**: 200
    
    * **Content**: `{ "message": "New vacation ID: 640" }`
    
* **Error response:**

    * **Code**: 400
    
    * **Content**: `{ "message": ERROR_MESSAGE, "status": 400, "statusText": "Bad request" }`
