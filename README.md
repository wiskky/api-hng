
# Building and deploying an API endpoints

## We are building and deploying a secure Python API hosted on AWS with Nginx reverse proxy and SSL encryption  

### To achieve this we make use of Python and FastAPI running on localhost 8000

## Clone repository 
git clone https://github.com/wiskky/api-hng.git
cd api-hng 

## Create virtual environment 
python3 -m venv venv 
source venv/bin/activate 

## Install dependencies 
pip install fastapi uvicorn 

## Run the application locally 
uvicorn main:app --reload --host 127.0.0.1 --port 8000 

## Test the endpoints 
curl http://127.0.0.1:8000/ 
curl http://127.0.0.1:8000/health 
curl http://127.0.0.1:8000/me 

## Live URL 
https://tekworld.name.ng 


### SSL is enabled using Let's Encrypt (Certbot), ensuring secure HTTPS communication with automatic redirect HTTP to HTTPS
