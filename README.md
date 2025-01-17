1. This is flask Api in python
2. Source: IBM full stack developement course
3. FLASK 

**In simpler terms:**

- **Request Object:** Imagine it as a package containing all the information a client sends to your Flask application when they make a request. This includes things like:
    - **What they're asking for:** The URL, the method (GET, POST, etc.).
    - **Who they are:** Their IP address, browser type (User-Agent).
    - **What they're sending:** Any data included in the request (form data, JSON, etc.).
    - **Cookies:** Any cookies they've previously received from your site.
- **Response Object:** This is like the package you send back to the client. It contains:
    - **The data:** The information you want to send back (HTML, JSON, images, etc.).
    - **Status code:** Tells the client if the request was successful (200 OK), or if there was an error (404 Not Found, 500 Internal Server Error).
    - **Headers:** Extra information, like the type of data being sent (e.g., "Content-Type: text/html").

**Key Concepts:**

- **Route Decorator (`@app.route`)**
    - Defines the URL path for a specific view function.
    - Can specify allowed HTTP methods (e.g., `methods=['GET', 'POST']`).
- **Accessing Request Data:**
    - `request.headers`: Access headers sent by the client.
    - `request.args`: Access query parameters.
    - `request.form`: Access form data.
    - `request.json`: Access JSON data in the request body.
- **Creating Custom Responses:**
    - `make_response()`: Create a custom response object.
    - `redirect()`: Redirect the client to another URL.
    - `abort()`: Return an error response.

By effectively using these objects, you can create dynamic and interactive web applications in Flask.
-------------------------------------------------------------------------------------------

Start the flask api server 
  ![image](https://github.com/user-attachments/assets/8df0070d-1618-49a3-89b1-bc84dd0cef92)

 
This is the code lets test it : 
![image](https://github.com/user-attachments/assets/00d0047c-9600-4bdd-ac6e-e34446a74d2d)


Test the flask api server if I can sent a customized rersponse from the server side
@app.route('/exp')   
![image](https://github.com/user-attachments/assets/aedc2d60-ce11-47f2-9a15-b1ba8b8bcf06)


@app.route('/no_content')
![image](https://github.com/user-attachments/assets/b3ff939f-dc02-4f5d-aa51-97ce155d1784)
result : ![image](https://github.com/user-attachments/assets/183bf9cd-c50d-4291-87cd-7308e7a30611)        


-----------------------------------------------------------------------------------
Process input arguments
It is common for clients to pass arguments in the URL. You will learn how to process arguments in this lab. The lab provides a list of people with their id, first name, last name, and address information in an object. Normally, this information is stored in a database, but you are using a hard coded list for your simple use case. This data was generated with Mockaroo.

The client will send in requests in the form of http://localhost:5000?q=first_name. You will create a method that will accept a first_name as the input and return a person with that first name.

4.Made a second file "lab2" in which made a "server2.py" file to practise this new code . 
Code ; 
![image](https://github.com/user-attachments/assets/d9aee154-0062-4575-8dde-6678c27f8aff)
![image](https://github.com/user-attachments/assets/1d3f2ca7-99cf-4865-94a8-9aa035c03a47)
![image](https://github.com/user-attachments/assets/cd20aaf6-fd32-4ca8-8cf3-2732f54c1a47)

If input a cprrect first name with no sellinf mistake and it is in the data then it gives:status :200 ok 
![image](https://github.com/user-attachments/assets/5ee40a89-2d7f-43a7-b058-dbe63c4b2de2)

If input is empty 422 status code 
![image](https://github.com/user-attachments/assets/81c63cfb-1289-4fcd-b5b7-d1bd8aaef70a)
![image](https://github.com/user-attachments/assets/10aca8f2-f728-4997-b0b7-ca3258da7dcc)

If input name is not present in data :  404 status

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Summary of RESTful API with Flask
This summary outlines the creation of a RESTful API using Flask, focusing on CRUD (Create, Read, Update, Delete) operations for a "person" resource.

Key Concepts:

RESTful API: A web API that adheres to REST (Representational State Transfer) principles, using URLs and HTTP methods to represent resources and actions.
CRUD Operations:
Create: Not implemented in this example, but typically involves a POST request to add a new resource.
Read:
/count: This endpoint (GET request) returns the total number of persons in the data list.
/person/<uuid:id>: This endpoint (GET request) retrieves a person by their unique identifier (UUID).
Update: Not implemented in this example, but typically involves a PUT request to modify an existing resource.
Delete: /person/<uuid:id>: This endpoint (DELETE request) removes a person from the data list based on their UUID.
UUID (Universally Unique Identifier): A unique identifier used to represent resources.
Flask Endpoints:
Decorators like @app.route and @app.route with methods (GET, DELETE) define URL paths and allowed HTTP methods for handling requests.
JSON Responses: Data is returned in JSON format for consistency and ease of use by clients.
Error Handling:
Status codes:
200 OK: Successful request.
404 Not Found: Resource not found (e.g., person with a non-existent UUID).
500 Internal Server Error: Unexpected error occurred.
Custom messages: Informative messages are provided in the JSON response body for clarity.
Code Breakdown:

count endpoint:
Attempts to return the length of the data list (number of persons) as a JSON response with a 200 status code.
Includes error handling for cases where data is not defined (500 status code with a message).
find_by_uuid endpoint:
Iterates through the data list to find a person matching the provided UUID.
If found, returns the person as a JSON response with a 200 status code.
If not found, returns a JSON response with a 404 status code and a "person not found" message.
delete_by_uuid endpoint:
Iterates through the data list to find a person matching the provided UUID.
If found, removes the person from the data list and returns a JSON response with a 200 status code and a confirmation message.
If not found, returns a JSON response with a 404 status code and a "person not found" message.
Overall Flow:

Client sends a request to a specific URL path (endpoint) with an appropriate HTTP method (GET, DELETE in this example).
Flask matches the request to a defined endpoint based on URL and method.
The corresponding function (e.g., find_by_uuid, delete_by_uuid) processes the request.
The function performs actions like retrieving data, modifying data, or returning error messages.
Flask returns a JSON response with relevant data or error information and a status code.
This is a simplified example of a RESTful API with Flask. More complex APIs may involve additional functionalities like authentication, authorization, and handling different data formats.






