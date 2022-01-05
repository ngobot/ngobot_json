# SIMPLE PYTHON JSON RESPONSE FORMAT 
The repository contain a script to format your function's response in a correct JSON format using the standard HTTP response codes. Well suitable to backend applications with REST API building concept in mind.

**Install the ngobot-json package**

`pip install ngobot-json`

**import the ngobot-json package**

`from ngobot_json.response import Response` 

instantiate it for a task as shown below

`response = Response()`

**1. Success Response**

you can simply return json successful response format in this way.

e.g.

`response = Response()

print(response.Success())
`

_Output:_


`{
"status":200,
"message":"Successful",
"data":{
"status":200,
"message":"ok",
"reason":"Successful"
}
}`

You can modify the json success response format by passing two arguments: (1) the data to return as response and (2) the keyword indicator "success" to activate success response format.

e.g. User Account Created.

`task = "User Account successfully created"

response = Response(task, "success")

print(response.Created())`

_Output:_

`{
"status":201,
"message":"Created Successfully",
"data":{
"status":200,
"message":"ok",
"reason":"User Account successfully created"
}
}
`


e.g. 2. Process completed successfully


`task = "The Process is successfully completed"

response = Response(task, "success")

print(response.Success())`



Output:


`{"status": 200, "message": "Successful", "data": {"status": 200, "message": "ok", "reason": "The Process is successfully completed"}}
`

**2. Error Response**

The error response follows the same pattern of the success modify response, but has a different keyword argument "error" to activate the error response format:

e.g.

`task = "Invalid username and password"

response = Response(task, "error")

print(response.Unauthorized())`

_Output:_

`{
"status":401,
"message":"Unauthorized",
"data":{
"status":422,
"message":"Unprocessable Entity",
"reason":"Invalid username and password"
}
}`



**3. Adding External json return from another function or database.**


e.g. 


`task = {
"status":201,
"message":"Created Successfully",
"data":{
"status":200,
"message":"ok",
"reason":"User Account successfully created"
}
}

response = Response(task, "data")

print(response.Success())`


Output:

`{"status": 200, "message": "Successful", "data": {"status": 201, "message": "Created Successfully", "data": {"status": 200, "message": "ok", "reason": "User Account successfully created"}}}
`



**4. List of All the supported HTTP codes functions to call.**

comming soon.




