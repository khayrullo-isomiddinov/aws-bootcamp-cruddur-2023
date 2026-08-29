# This file is for building an image. 

# image is for creating containers. 

FROM python:3.10-slim-buster

# inside container  
# make a new folder inside the container 
WORKDIR /backend-flask

# outside container -> inside container 
COPY requirements.txt requirements.txt

# inside container 
# install the python libs to be used for the app
RUN pip3 install -r requirements.txt

# outside container -> inside container 
# everything in the current directory. first period  = everything in backend flask outside the container. second period is the one inside the container. 
COPY . .

# set env vars 
# inside the container 
ENV FLASK_ENV=development

ENV FLASK_DEBUG=1

EXPOSE 4567

CMD ["python3", "-m", "flask", "run", "--host=0.0.0.0", "--port=4567", "--debug"]

