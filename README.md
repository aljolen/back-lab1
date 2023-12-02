# back-lab1
The web application for Lab 1
# Installation

## 1. Clone git repo

    git clone https://github.com/aljolen/back-lab1.git
    cd back-lab1

This webapp can be then run using on of these three methods:

## 2.1 Using local python interpreter

Create and activate a new virtual environment (Skip if you want the packages to be installed globally):

    python -m venv env
    .\env\Scripts\activate

Install the needed requirements and run the app

    python -m pip install -r requirements.txt 
    flask --app webapp run -p 8080 

The webapp will be accessible under http://localhost:8080
    

## 2.2 Using docker
Build the `Dockerfile` and run it 

    docker build -t <your-tag>:latest .
    docker run --rm -e PORT=80 -p 8080:80 <your-tag>:latest

The webapp will be accessible under http://localhost:8080
    


## 2.3 Using docker compose
To build and run the whole web service, just run: 

    docker compose up
The web service will be accessible under http://localhost:8080/ <br>
By default, it can be accessed under the port <code>8080</code> <br>
The exposed port of the container by default is <code>80</code>

You can change the values for the both ports in the <code>docker-compose.yaml</code> 
file:

    ...
    environment:
      PORT: <CONTAINER-PORT>
    ports:
      - "<HOST-PORT>:<CONTAINER-PORT>"
    ...

# Deployed instance

The deployed webapp service is available under https://back-lab1.onrender.com/ <br>
The health check can be performed using https://back-lab1.onrender.com/healthcheck