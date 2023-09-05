FROM python:3.8-slim-buster
WORKDIR /python-docker
COPY requirements.txt .
RUN pip3 install -r requirements.txt
RUN apt-get update && apt-get install -y vim net-tools nginx wget
COPY . .
EXPOSE 5000
CMD [ "python3", "app.py"]
