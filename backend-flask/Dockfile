FROM python:3.10-slim-buster 
# looks for and runs a docker image from docker hub recursively until you reach scratch (which is an empty image)

WORKDIR /backend-flask
# make a new folder inside the container 

COPY requirements.txt requirements.txt
# copy from outside the container to inside the container
# text files contains the libraries we want to install to run the app

RUN pip3 install -r requirements.txt
# inside the container
# install the python libraries used to run the app

COPY . .
# from outside the container to inside the container
# generally . means everything in the current directory
# first period . represents /backend-flask (inside the container)
# second period . represents /backend-flask (outside the container)

ENV FLASK_ENV=development
# set environment variables inside the container

EXPOSE ${PORT}

CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
# -m flask = run the flask module
# bind host to 0.0.0.0
# port number can be anything