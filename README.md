# ngobot_json
The repository contain a script to format your method's response in a correct JSON format using the standard HTTP response codes. Well suitable to backend applications with REST API building concept in mind.

# Installation
Install the ngobot-json package

pip install ngobot-json

import the ngobot-json package

from ngobot_json.response import Response

instantiate the package for a task as shown below

Success Response

the success response task are shown below contain two arguments (1) the data to return as response and (2) the keyword indicator "success":

e.g.

task = "User Account successfully created"

response = Response(task, "success")
print(response.Success())

Output:
{
   "status":200,
   "message":"Successful",
   "data":{
      "status":200,
      "message":"ok",
      "reason":"User Account successfully created"
   }
}

Error Response

the error response follows the same pattern of the success response but has a different keyword argument "error"

e.g.

task = "Invalid username"

response = Response(task, "error")
print(response.Unauthorized())

Output:

{
   "status":401,
   "message":"Unauthorized",
   "data":{
      "status":422,
      "message":"Unprocessable Entity",
      "reason":"Invalid username"
   }
}

