# flaskapp
Docker image building of a simple Flask App

STEP 1 - TESTING APP ON MACHINE USING VIRTUAL ENVIRONMENT

sudo yum install python-virtualenv

mkdir project   #Create a folder for project

cd project      #Go inside the directory

python3 -m venv myenvironment   #Start a virtual environment

source myenvironment/bin/activate   # Now you will work inside the environment

pip install Flask     #Install Flask inside env

vi app.py             #Project code

export FLASK_APP=app.py    #Define a env variable

python3 app.py       # Run the application

----------------------------------------------------------------------
![image](https://user-images.githubusercontent.com/92083624/196700198-7ae89f03-19c4-4a00-9ce5-41d195afdafc.png)
----------------------------------------------------------------------


YOUR APPLICATION CAN BE VIEWED IN:
LOCALHOST : Use Curl to see it: curl http://10.1.0.4:5000/

OUTSIDE THE VM: ON WEB BROWSER: VM-IP:5000    (OPEN 5000 PORT FOR THE VM)


STEP 2 - CREATING DOCKER IMAGE OF APPLICATION AND RUNIING IT

1. Install Docker
2. Write Dockerfile and requirements.txt files

3. docker build -t myapplication .             #This will create image of application and name it "myapplication"

To see image: docker images

![image](https://user-images.githubusercontent.com/92083624/196700474-98d7ea22-3127-479c-bba6-e54d371ef1e1.png)


4. docker run -d -p 80:5000 myapplication      # Run a container with this image. The application's output at port 5000 is mapped with 80 of VM

To see container: docker ps

![image](https://user-images.githubusercontent.com/92083624/196700755-34818dc7-567a-49c1-8d0c-ffdccc8e1ad0.png)

OUTPUT CAN BE SEEN AT: VM-IP:80 on Web browser

5. docker logs container-id                 # To see actions inside container when you try to access the output on web browser

Output from Continer at IP:80

![image](https://user-images.githubusercontent.com/92083624/196701324-80a92be5-9313-4ede-a5ab-bec264fd0fde.png)
