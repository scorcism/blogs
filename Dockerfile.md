 ## Let's start
 
 **Clone** [this repo](https://github.com/DevOpsProjectOps/react-counter)
 
 It's a simple react app which increase the count on the button clicks and store in localstorage to maintain state.

**Dockerfile explanation**

Lets break the code into componets

```dockefile 

FROM  node:20-alpine3.17

WORKDIR  /app

COPY  ./package.json  .

RUN  npm  install

COPY  .  .

EXPOSE  3000

CMD  [  "npm","start"  ]

```

Every new line or new line command in the Dockerfile is a new layer on top of the previous one.

Docker creates container images using layers. Each command that is found in a Dockerfile creates a new layer.

Each layer contains the filesystem changes to the image for the state before the execution of the command and the state after the execution of the command.

```dockerfile 
FROM  node:20-alpine3.17
```
This creates a base layer for our application. Since we are using `react`, we require `node` as the base. You can choose any base image, e.g., Ubuntu, but in Ubuntu images we have to manually download `node`, so instead we can use the node image itself.

```dockerfile 
WORKDIR  /app
```
`WORKDIR` changes the working directory for future commands.
The `WORKDIR` specifies the default directory inside a Docker container where commands will be executed.
It is similar to the concept of the current working directory on your computer when you run commands in the terminal or command prompt.

```dockerfile
COPY  ./package.json  .
```
This line copies the `package.json` file from the current directory on the host machine (where the Dockerfile is located) into the `/app` directory inside the container. 
It's the first step in installing the dependencies required for the Node.js application.

```dockerfile
RUN  npm  install
```
This line runs the `npm install` command inside the container. 
It installs all the dependencies listed in the `package.json` file into the `/app/node_modules` directory inside the container. 
These dependencies are required for the Node.js application to work correctly.

```dockerfile
COPY  .  .
```
This line copies all the files and folders from the current directory on the host machine into the `/app` directory inside the container. 
This includes all the source code and other files needed for the Node.js application.

```dockerfile
EXPOSE  3000
```
This line exposes port 3000 inside the container. 
It means that the container will listen for incoming connections on port 3000, which is a common port used for web applications.

```dockerfile
CMD  [  "npm","start"  ]
```
This line sets the default command to be executed when the container starts running. 
It runs the `npm start` command, which typically starts the Node.js application defined in the `package.json` file. 
So, when the container starts, it will run the `react` application and listen on port 3000 as specified earlier with `EXPOSE`.

---

Now, as we got the undertsanding of `Dockerfile` 
Now we will explore some commands to `create a Docker image` and a `Docker container`.

**Create image from DockerFile**
```bash  
docker build -t react-counter .
``` 
-   `docker build`: This tells Docker to start building a new image.
-   `-t react-counter`: This specifies the name of the image we want to create. In this case, the image will be named "react-counter."
-   `.`: This indicates the current directory, where the Dockerfile (the configuration file that defines the image) is located. 
	- Docker will look for the Dockerfile in the current directory and use it as a blueprint to create the image.

**Create Container of Docker Image**
 ```bash 
 docker run -name counter1 -d -p 4000:3000 react-counter
```
-   `docker run`: This tells Docker to run a new container.
-   `-name counter1`: This sets the name of the container as "counter1". 
	- The name is like a nickname for the container so that you can refer to it easily later.
-   `-d`: This flag runs the container in the background (detached mode) so that you can continue using your terminal.
-   `-p 4000:3000`: This maps port 4000 on your host machine to port 3000 inside the container. 	
	- It means you can access the application running inside the container on your host machine using port 4000.
-   `docker-img-id` or `docker-img-name`: This is the unique identifier (ID) of the Docker image that you want to run in the container. 
	- Docker uses this ID to find the image and create a container from it.
	
**Open you browser**

Enter the [URI](https://www.techtarget.com/whatis/definition/URI-Uniform-Resource-Identifier) 
	
```http://localhost:4000/```

**ENJOY**
