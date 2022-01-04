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

You can modify the json success response format by passing two arguments: (1) the data to return as response and (2) the keyword indicator "success" to signify success response.

e.g.

`task = "User Account successfully created"

response = Response(task, "success")
print(response.Success())`

_Output:_

`{
"status":200,
"message":"Successful",
"data":{
"status":200,
"message":"ok",
"reason":"User Account successfully created"
}
}
`

**2. Error Response**

The error response follows the same pattern of the success modify response, but has a different keyword argument "error" to signify the error response:

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


more updates are coming soon.




