# Nginx_docker_static_website
#Documentation:
##Task: Build a docker image for static website then run and publish it to docker hub.
---
##Prerequisites:
1. Install docker in your Operating System
2. Create an account at [DockerHub](https://hub.docker.com/)

#From the above task we need to perform three basic action these are:
 ``` 
     i) build 
     ii) run 
     iii) push
 ```
     
---
 
## To build and run an image for static-website just go for the following steps and commands:

Step 01: Make a folder  (for example: DockerLab)
Step 02: In this for create two file say one is index.html another one is Dockerfile
Step 03: In the index.html file just put your own html code for now you can simply copy and paste the follwing code:
```  
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <h5>This is a simple web page</h5>
    </body>
    </html>
```
and then save it.

Step 04: In the Dockerfile just place the following code and save it.
```
    FROM nginx:alpine
    COPY . /usr/share/nginx/html/test 
```
Great Job! your website and basic configureation is ready now.

Step 05: Now open your command line with the working directory(folder) then copy and paste the following command:
```
   Syntax: sudo docker build -t username_of_dockerhub/image_name .
   (for example: sudo docker build -t saiful321/demodockerlab .) 
```
Wow! you have successfully build the image.


Step 06:(To run the image)
```   
   Syntax: sudo docker run -p 8080:80 -d username_of_dockerhub/image_name
   (for example: sudo docker run -p 8080:80 -d saiful321/demodockerlab) 
```

Step 07: Now it is time to see the website, to do so just copy and paste the follwing line into the browser search bar: 
```
   0.0.0.0:8080/test 
```

Boom! you see your website is running.
---
---
## To publish image into dockerhub use the following command:
At first you need to login into docker hub with your user_name and password.

```sudo docker login```

After that publish your image by the following command:

```Syntax: sudo docker push user_name_of_dockerHub/your_image_name
   sudo docker push saiful321/demodockerlab
```
well done! now go to the dockerhub website and refresh it as a result you will see your published image.
---


## Extra command:
To restart and check the docker if you face any issue:
```
    $ sudo systemctl daemon-reload #THIS IS RESCUE COMMAND…
    $ sudo systemctl restart docker
    $ sudo systemctl status docker 
```
