# Layers 
The order of Dockerfile instructions matters

## Cached layers
example:
  # syntax=docker/dockerfile:1
  FROM golang:1.21-alpine
  WORKDIR /src
- COPY . .
+ COPY go.mod go.sum .
  RUN go mod download
+ COPY . .
  RUN go build -o /bin/client ./cmd/client
  RUN go build -o /bin/server ./cmd/server
  ENTRYPOINT [ "/bin/server" ]

Cached means reuse
when we run build, builder would attempt to reuse layer from earlier builds
if change project files, would invalidate the cache for the copy layer, also invalidates the cache for all of the layers that follow

