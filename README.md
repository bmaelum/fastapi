# FastAPI Tutorial
This repo is for learning how to use FastAPI.

## Tutorial
The code in this tutorial is found in the official documentation for FastAPI: https://fastapi.tiangolo.com/.

## Deployment Tutorial
https://towardsdatascience.com/deployment-could-be-easy-a-data-scientists-guide-to-deploy-an-image-detection-fastapi-api-using-329cdd80400 

### Accessing the server
The server is an Ubuntu 18.4 LTS on AWS and can be connected using the following command where the .pem file is the SSH key: 
```
ssh -i "fastapi.pem" ubuntu@ec2-34-253-214-90.eu-west-1.compute.amazonaws.com
```


### Building the docker image
```
sudo docker build -t fastapi-image .
```

### Starting the docker container
```
sudo docker start fastapi-container
```

### Accessing the app
#### Docs
http://ec2-34-253-214-90.eu-west-1.compute.amazonaws.com/redoc

## Getting Started
### Requirements
Make sure you have installed the requirements found in requirements.txt in a virtual environment using tools such as conda or virtualenv.

### Running the code
```
uvicorn main:app --reload
```



### Sample Request
#### Python
```
import requests

url = "localhost:8000/items/2"

payload="{\n    \"name\": \"string\",\n    \"price\" : 0\n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("PUT", url, headers=headers, data=payload)

print(response.text)
```

#### Curl
```
curl --location --request PUT 'localhost:8000/items/2' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "string",
    "price" : 0
}'
```




