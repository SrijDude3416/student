---
toc: False
comments: True
layout: default
title: Data Structures Writeup
description: Write up on the data structures project
type: tangibles
courses: {'compsci': {'week': 12}}
---


# Collections

Blog Python Model code and SQLite Database.

- From VSCode using SQLite3 Editor, show your unique collection/table in database, display rows and columns in the table of the SQLite database.

<a href="https://ibb.co/k5my7zz"><img src="https://i.ibb.co/VJwN1bb/database1.png" alt="database1" border="0"></a>
What is shown above is the designs collection within my database which contains the various designs saved including username of owner for identification and content.

- From VSCode model, show your unique code that was created to initialize table and create test data.

<a href="https://ibb.co/x6fMQcG"><img src="https://i.ibb.co/HqxrQMY/database2.png" alt="database2" border="0"></a>
What is shown above is the intialization of the Design model object. We declare varaibles such as design type, content, name, and more. 

# Lists and Dictionaries

Blog Python API code and use of List and Dictionaries.

- In VSCode using Debugger, show a list as extracted from database as Python objects.

<a href="https://ibb.co/M8tm4FR"><img src="https://i.ibb.co/4sXHGhj/lists1.png" alt="lists1" border="0"></a>
This screenshot is taken in debugger after running the search function. We see multiple Design objects which have been freshly loaded from our database.

- In VSCode use Debugger and list, show two distinct examples of dictionaries, show Keys/Values using debugger.
<a href="https://ibb.co/7YHhd6y"><img src="https://i.ibb.co/98JPkCY/lists2.png" alt="lists2" border="0"></a>
The screenshot above is taken in debugger and shows the request body json for logging in.
<a href="https://ibb.co/yQpqQMN"><img src="https://i.ibb.co/kSJXSrG/lists3.png" alt="lists3" border="0"></a>
The screenshot above is taken in debugger and shows the request body json when saving a design.


# APIs and JSON

Blog Python API code and use of Postman to request and respond with JSON.

- In VSCode, show Python API code definition for request and response using GET, POST, UPDATE methods. Discuss algorithmic condition used to direct request to appropriate Python method based on request method.

<a href="https://ibb.co/HptXq2c"><img src="https://i.ibb.co/vv3DkBN/apis1.png" alt="apis1" border="0"></a>
The screenshot above is taken from the users api file and shows the definition of CRUD operations that are run after POST, GET, or PUT requests.

- In VSCode, show algorithmic conditions used to validate data on a POST condition.

<a href="https://ibb.co/rQGCmjL"><img src="https://i.ibb.co/yNnwX9M/apis2.png" alt="apis2" border="0"></a>
The code in the screenshot above checks to see whether certain variables in the request body json are None or not. If they are, then they will be updated into the user's entry in the collection in the database.

- In Postman, show URL request and Body requirements for GET, POST, and UPDATE methods.
- In Postman, show the JSON response data for 200 success conditions on GET, POST, and UPDATE methods.
<a href="https://ibb.co/6np99zv"><img src="https://i.ibb.co/xCc99Wm/apis3.png" alt="apis3" border="0"></a>
<a href="https://ibb.co/NZjGr1Y"><img src="https://i.ibb.co/72W0Qgy/apis4.png" alt="apis4" border="0"></a>
<a href="https://ibb.co/XZ4VGtM"><img src="https://i.ibb.co/VWN3kT5/apis5.png" alt="apis5" border="0"></a>
<a href="https://ibb.co/kMCw7rc"><img src="https://i.ibb.co/qxQcS41/apis6.png" alt="apis6" border="0"></a>

- In Postman, show the JSON response for error for 404 when providing an unknown user ID to a UPDATE request.
<a href="https://ibb.co/L0pwb7f"><img src="https://i.ibb.co/zmfcjvw/apis7.png" alt="apis7" border="0"></a>


# Frontend

Blog JavaScript API fetch code and formatting code to display JSON.

- In Chrome inspect, show response of JSON objects from fetch of GET, POST, and UPDATE methods.

<a href="https://ibb.co/kmVQDrt"><img src="https://i.ibb.co/9Zms4f7/frontend1.png" alt="frontend1" border="0"></a>
The screenshot above is taken after running a fetch request to the search endpoint in the backend. The console on the right displays the json data returned by the backend.

- In the Chrome browser, show a demo (GET) of obtaining an Array of JSON objects that are formatted into the browsers screen.
    - In JavaScript code, describe fetch and method that obtained the Array of JSON objects.

<a href="https://ibb.co/K0BRVjc"><img src="https://i.ibb.co/8KGTPDn/frontend2.png" alt="frontend2" border="0"></a>
The screenshot above shows the frontend displaying multiple objects after iterating through the results provided from the backend.

- In JavaScript code, show code that performs iteration and formatting of data into HTML.
<a href="https://ibb.co/CHgBKyY"><img src="https://i.ibb.co/Krd6xgf/frontend3.png" alt="frontend3" border="0"></a>
The screenshot above shows the code that allows the frontend to do it.

- In the Chrome browser, show a demo (POST or UPDATE) gathering and sending input and receiving a response that show update. Repeat this demo showing both success and failure.
- In JavaScript code, show and describe code that handles success. Describe how code shows success to the user in the Chrome Browser screen.
<a href="https://ibb.co/GvYtLX5"><img src="https://i.ibb.co/N6DmPXy/frontend5.png" alt="frontend5" border="0"></a>

The screenshot above shows the browser rerouting a successful result to the home page.

- In JavaScript code, show and describe code that handles failure. Describe how the code shows failure to the user in the Chrome Browser screen.
<a href="https://ibb.co/vDcJ3vW"><img src="https://i.ibb.co/9Gpqb30/frontend4.png" alt="frontend4" border="0"></a>
The screenshot above shows the browser rerouting an unsuccessful result to the 401 error page. 

# Optional/Extra, Algorithm Analysis

In the ML projects, there is a great deal of algorithm analysis. Think about preparing data and predictions.

- Show algorithms and preparation of data for analysis. This includes cleaning, encoding, and one-hot encoding.
<a href="https://ibb.co/4JdmJVh"><img src="https://i.ibb.co/0QtDQGH/ML1.png" alt="ML1" border="0"></a>

- Show algorithms and preparation for predictions.
<a href="https://ibb.co/Z6TY9Bj"><img src="https://i.ibb.co/ynsY269/ML2.png" alt="ML2" border="0"></a>

- Discuss concepts and understanding of Linear Regression algorithms.
  
Linear regression is like finding the best-fit line through a bunch of points on a graph. Picture this: you have data points scattered on a graph, and you want to draw a straight line that comes closest to touching all of them. That's what linear regression does. It helps us understand the relationship between two things. For example, if we're trying to predict the price of a house based on its size, linear regression helps us figure out how much the price changes for each additional square foot. It's pretty handy in making predictions, but it does have some rules. For instance, it assumes that the relationship between the variables is straight and not curved, and that the points are spread out evenly. Overall, it's a simple yet powerful tool for understanding and predicting things in the real world.

- Discuss concepts and understanding of Decision Tree analysis algorithms.

Decision trees are a bit like playing a game of 20 Questions. You start with a question at the top, like "Is it bigger than a breadbox?" Based on the answer, you move down the tree to another question, like "Is it green?" And so on, until you reach the end and find your answer. In the world of data, decision trees help us make decisions by breaking down a problem into smaller, simpler decisions. Each "question" in the tree is based on a feature of the data, like the size or color of something. By asking these questions in a certain order, the tree can learn to make accurate predictions or classifications. It's a neat way to organize and understand data, and it's especially useful when there are lots of different factors to consider. Plus, decision trees are easy to interpret, making them a favorite tool for data scientists and analysts alike.
