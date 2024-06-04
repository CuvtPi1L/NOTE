# Image
Read only templates


possible structure:
.
├── Dockerfile
├── cmd
│   ├── client
│   │   ├── main.go
│   │   ├── request.go
│   │   └── ui.go
│   └── server
│       ├── main.go
│       └── translate.go
├── go.mod
└── go.sum

## Docker File
'''Dockerfile
# syntax=docker/dockerfile:1
FROM golang:1.21-alpine
WORKDIR /src
COPY . .
RUN go mod download
RUN go build -o /bin/client ./cmd/client
RUN go build -o /bin/server ./cmd/server
ENTRYPOINT [ "/bin/server" ]
'''

1. FROM 
FROM golang:1.21-alpine
The FROM instruction uses version 1.21-alpine of the golang official image.

2. WORKDIR 
   WORKDIR /src 
Create the working dirctory in the container

3. COPY
	COPY . .
copy building(your side) code into container

4. RUN 
   RUN go mod download
Download necessary modules, same for pip install, npm install, RUN is running in the CLI in the container

	RUN go build -o /bin/client ./cmd/client
runing in the client side
	RUN go build -o /bin/server ./cmd/server
Building in the server side

5. ENTRYPOINT [ "/bin/server" ]
Specifies a command to run when the container starts. Starts the server process.

## Build the image
 docker build --tag=buildme .
 -t is --tag=
 . is for the dir you are in

## Run the container
 docker run --name=buildme --rm --detach buildme
 Run a container from the image in detached mode.
 This starts a container named buildme.

 docker run buildname

  docker exec -it buildme /bin/client
	Run a new command in the buildme container that invokes the client binary.
The docker exec command opens a terminal user interface 

When you're done testing, you can stop the container:
	"""bin because of the docker container sructure"""
### Flags
docker run --name <container name:webapp> -d<detached> -p<port> 9000:8000 <image:niginx:1.23>











