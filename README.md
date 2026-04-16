# Building and deploying an API endpoints

## We are building and deploying a secure Python API hosted on AWS with Nginx reverse proxy and SSL encryption  

### To achieve this we make use of Python and FastAPI running on localhost 8000

## Clone repository 
``` 
git clone https://github.com/wiskky/api-hng.git
cd api-hng 
``` 

## Create virtual environment 
```
python3 -m venv venv 
source venv/bin/activate 
``` 

## Install dependencies 
`pip install fastapi uvicorn `

## Run the application locally
To be able to run our API automatically/ to keep the  API running I included the below in this directory /etc/systemd/system/api.service 

```
[Unit]
Description=FastAPI App
After=network.target

[Service]
User=ubuntu
WorkingDirectory=/home/ubuntu/api-hng
ExecStart=/home/ubuntu/api-hng/venv/bin/uvicorn main:app --host 127.0.0.1 --port 8000
Restart=always

[Install]
WantedBy=multi-user.target
```

So there is no need to run below command before running it locally.
`uvicorn main:app --reload --host 127.0.0.1 --port 8000` 

## Test the endpoints 
```
curl http://127.0.0.1:8000/ 
curl http://127.0.0.1:8000/health 
curl http://127.0.0.1:8000/me 
``` 

## Live URL 
(https://tekworld.name.ng)  


### SSL is enabled using Let's Encrypt (Certbot), ensuring secure HTTPS communication with automatic redirect HTTP to HTTPS
