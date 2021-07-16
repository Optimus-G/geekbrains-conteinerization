#image alpine
FROM golang:1.14-alpine

# Author
MAINTAINER Optimus-G

#Directory for app
WORKDIR /app

# Download necessary Go modules
COPY go.mod .
COPY go.sum .
RUN go mod download

#Copy all in image
COPY *.go .

#Compile go_app
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o /server .


#Image listen port
EXPOSE 8080

#command executed at run
CMD [ "/server" ]
