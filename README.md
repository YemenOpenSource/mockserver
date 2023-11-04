[![Stand With Palestine](https://raw.githubusercontent.com/TheBSD/StandWithPalestine/main/banner-no-action.svg)](https://TheBSD.github.io/StandWithPalestine/)

This is just a sample Mockserver and you can change or customize it to fit your needs using the provided examples in the code.

To start:

1- Clone this repo

2- cd to mockserver dir

3- run "docker-compose up"

The server will start on port 1080 by default " - http://localhost:1080/" but you can change that in the yml file.

To test the API open postman and make a get request to the following endpoints:

1- POST "http://localhost:1080//api/v1/image/upload" this endpoint accepts an image and returns json response:

{
"Result": "Success",
"Message": "Image is being processed (File: image.png Size: 475Kb)",\
"processId": 1
}

*There are two other endpoints Get status and get result of processed image but you can have as money endpoints as you want.

2- Mockserver also comes with a UI dashboard and you can access it here: http://localhost:1080/mockserver/dashboard

The Repo containes two files:
1- docker-compose.yml - here we have all the configureation we need for the mockserver
2- initializer.json - here we have all our request response forammted api calls

For detailed documentation and other options check below URL:
https://www.mock-server.com/mock_server/running_mock_server.html#docker_container

You can also check the mockserver UI dashboard to check when api calls dont match


NOTE: 
The last two requests are error handling lets take the endpoint "/api/v1/image/status" line 72, as an example:
To call the status endpoint you need to provide a processId with value of "1" because its the only endpoint we added so if you provided a processId with a value other than 1 you will get the default response which is "Bad Request! Invalid or missing processId" and thats how we do error handling, the body is generic not specific values.


