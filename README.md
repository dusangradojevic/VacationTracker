![image](https://user-images.githubusercontent.com/55301074/219312228-c049a5a7-ad38-4035-98bc-d406af904657.png)

## Install library

    cd database
    mvn clean install

The REST endpoint for reminder submitting:
* {site-url}/reminders/add (HTTP POST method)

Reminder is passed as an argument in a body in JSON format and has the following attributes: 
* String user - who is posting a reminder
* Array<String> receivingUsers - for whom is a reminder intended for
* String msg - reminder name
* Date date (yyy-MM-dd) - date when receiving users should be reminded

Example for adding a reminder:

* localhost:8080/reminders/add

* Body:  
{  
&nbsp;&nbsp;&nbsp;&nbsp; "user" : "JohnDoe",  
&nbsp;&nbsp;&nbsp;&nbsp; "receivingUsers" : [  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "JaneDoe", "JamesSmith", "RobertJones"  
&nbsp;&nbsp;&nbsp;&nbsp; ],  
&nbsp;&nbsp;&nbsp;&nbsp; "msg" : "Team meeting",  
&nbsp;&nbsp;&nbsp;&nbsp; "date" : "2021-10-02"  
}  

The REST endpoint for getting reminders for the specified user on the specified date:

* {site-url}/reminders/get/{user}/{date} (HTTP GET method)

* Date should be passed in format yyyy-MM-dd.

Example for getting a reminder:

* localhost:8080/reminders/get/JaneDoe/2021-10-02
