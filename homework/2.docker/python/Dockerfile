# syntax=docker/dockerfile:1

#image alpine
FROM python:3.9.6-alpine

# Author
MAINTAINER Optimus-G

#Directory for app
WORKDIR /app

# Create user and set ownership and permissions as required
RUN adduser -D pyuser && chown -R pyuser /app

#Copy requirements in workdir
COPY requirements.txt requirements.txt

#Install requirements
RUN pip3 install -r requirements.txt

#Copy all files in image
COPY . .

#Image listen port
EXPOSE 8080

#Use user pyuser
USER pyuser

#command executed at run 
ENTRYPOINT python /app/app.py runserver 0.0.0.0:8080
