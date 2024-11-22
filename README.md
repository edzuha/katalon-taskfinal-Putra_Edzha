# katalon-taskfinal-Putra_Edzha

# **Objective**
This application focuses on contains projects from WEB, API, and mobile.

# **App Usage Guide**
**Requirements that must be inserted before running this application are :**
* Using Groovy language based on Katalon Studio ```version 9.7.2```
* Testing is done on the End-Point API provided by [herokuapp](https://restful-booker.herokuapp.com/)
* Testing is done on the End-Point WEB provided by [OWASP juice shop](https://juice-shop.herokuapp.com/)
* Testing is done on the End-Point Mobile provided by android (Todo.apk)
* Testing was carried out with the Google Chrome Website Browser ```Version 130.0.6723.117``` (Official Build) (64-bit)

# **Summary of Testing Results**
In the implementation of testing, testing was carried out on 27 Test Cases with the results:
```
27 Passed
0 Failed
0 Not Executed
```
So the test result is 100% Passed

# **Report**
In testing, if you have to test one test case at a time, it will take a long time, so a **Test Suite** is made, so that you can run several test cases simultaneously, namely:

**API Project:**
```
TS E2E Booking
```
In the **Test Suite** there are 5 test cases:
```
TC Create Booking
TC Get Booking IDs
TC Update Booking
TC Delete Booking
TC Ping
```
**WEB project:**
```
TS Register
TS Login
```
In the **Test Suite Register** there are 2 test cases:
```
TC Register
TC Register password do not match
```
In the **Test Suite Login** there are 5 test cases:
```
TC Login
TC Login Failed email invalid
TC Login Failed password invalid
TC Login Failed email empty
TC login Failed password empty
```
**Mobile project:**
```
TS Create Task
TS Update Task
```
In the **Test Suite Create Task** there are 3 test cases:
```
TC Create Task
TC Title Empty
TC Task Empty
```
In the **Test Suite Update Task** there are 5 test cases:
```
TC Create Task
TC Edit Task
TC Copy Task
TC Share Task
TC Delete Task
```

# **End Point**
The overall endpoints in this project are :

First create new ```staging``` profiles that contain global variables

**API project:**
```
baseURL = https://restful-booker.herokuapp.com/
username_admin = admin
pass_admin = password123
refresh_token = ""
refresh_ID = ""
```
**WEB project:**
```
URLbase = https://juice-shop.herokuapp.com/
email_regist = "edzhasaaa@gmail.com"
email_wrong = ""
pass_regist = "alcjMy+dkSIt0wL4F4pTwA=="
pass_wrong = ""
security_middle_name = "Edzha"
search_item = "Apple"
```
In each Object Repository, add local variables

**API project:**
```
host = GlobalVariable.baseURL
username = GlobalVariable.username_admin
paswword = GlobalVariable.password_123
token = GlobalVariable.refresh_token
ID = GlobalVariable.refresh_ID
```
**WEB project:**
```
host = GlobalVariable.URLbase
email = GlobalVariable.email_regist
password = GlobalVariable.pass_regist
middle_name = GlobalVariable.security_middle_name
search = GlobalVariable.search_item
email_wrong = GlobalVariable.email_wrong
pass_wrong = GlobalVariable.pass_wrong
```
# **For the following API project:**

**POST Create Token**

To Create Token, provided 1 pages that will generate a response code ```200 OK``` and result user
```
${host}/auth
```
**POST Create Booking ID**

```
${host}/booking
```
To create id, by entering in the ```HTTP BODY``` with the ```TEXT``` and ```JSON``` attributes, which will produce a ```200 OK``` response code and the results of adding data:
```
{
    "firstname" : "Putra",
    "lastname" : "edzha",
    "totalprice" : 4800,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2024-11-01",
        "checkout" : "2024-11-03"
    },
    "additionalneeds" : "Dinner"
}
```
**GET Booking IDs by ALL ID**

Used for viewing all IDs
```
${host}/booking
```
**GET Booking IDs by ID**

View one of the IDs that have been created
```
${host}/booking/${ID}
```
**GET Booking IDs by Name**

View one of the IDs that have been created by filling in the firstname and lastname
```
${host}/booking?firstname=Putra&lastname=Edzuha
```
**PUT Update Booking ID**
```
${host}/booking/${ID}
```
To update id, by entering in the ```HTTP BODY``` with the ```TEXT``` and ```JSON``` attributes, which will produce a ```200 OK``` response code and the results of adding data:
```
{
    "firstname" : "Putra",
    "lastname" : "edzha",
    "totalprice" : 48000,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2024-11-01",
        "checkout" : "2024-11-03"
    },
    "additionalneeds" : "Massage"
}
```
**PATCH Partial Update Booking ID**
```
${host}/booking/${ID}
```
To partial update id, by entering in the ```HTTP BODY``` with the ```TEXT``` and ```JSON``` attributes, which will produce a ```200 OK``` response code and the results of adding data:
```
{
    "firstname" : "Putra",
    "lastname" : "Edzuha"
}
```
**DELETE Booking ID**

To delete ID, Will generate response code ```201 OK``` and ```Created```, because it has been deleted.
```
${host}/booking/${ID}
```
# **WEB project:**
