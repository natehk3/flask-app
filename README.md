# Simple Python Flask Dockerized Application#

Build the image using the following command. We told Docker to build an image from our 
Dockerfile. We 'tagged' the image as 'simple-flask-app:latest' using the 't' flag.
Docker images are usually tagged with <name>:<version>. The trailing '.' tells Docker
where to look for the Dockerfile (in the current directory).

```bash
$ docker build -t simple-flask-app:latest .
```

Run the Docker container using the command shown below. The '-d' flag tells Docker to start
the container detached so it outputs the container id and returns to the console. The container
is still running however. We didn't specifya command so the container is running the command 
specified in the Dockerfile.

```bash
$ docker run --name flask1.0 -d -p 5000:5000 simple-flask-app
```

The application will be accessible at http:127.0.0.1:5000 or if you are using boot2docker then first find ip address using `$ boot2docker ip` and the use the ip `http://<host_ip>:5000`

To connect to the running container and test the web server run the following command
```bash
$ docker exec -i -t flask1.0 /bin/bash
```