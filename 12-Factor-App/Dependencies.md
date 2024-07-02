Explicitly declare and isolate dependencies.

Let's start with the example so we can fully undestand by end of the course.

For example, we installed the flask framework a python web application framework pror to writig our code. Therefore it is essential to install the flask python framework in our local dev env before beginning the development. This is just one dependency of our flask web application. But when we keep growing, we may have many third-party dependency.
    $ pip install flask

    on app.py you will have "from flask inport Flask"

The most importend we need to rember is that "A twelve-factor app never relies on implicit existence of system-wide packages. Meaning you cannot assume that the dependencies such as flask in this case will exist on the system where you will be running your app. So this rule in the12 factor app recommends to explicity declare an isolate dependencies. 

Many application have multiple dependencies that must be instaled prior to running the application. In the case of python this dependencies are tupically listed in a file named requirments.txt in the specific formate like this.
    file name: requirements.txt
        flask=2.0.0

It's importend to know the each version number is specified after the package name. Without this the different developer may install different version leading to inconsistencies when the program is run in different env. for example when dev run into one versino during development and by the time it goes to production the operation team may installed a different version without dev know. This could cause the app to not function as expected. However in the end the pip install command will take care all the dependencies listed in the requirements file during the build process. 

Now let's talk about the isolationg the dependencies which is the second part of this rule. 

Let's say we are working on developing two separate services or separate application on oir laptop and if one app requires one versino of flask and another require another version. It is a best practice to create an isolated environment for our application that includes all the necessary dependencies. Different programming language provide different approaches. For example, python has a concept of virtual environments(Venv). With Venv, we acn create an isolated environment for each application with it's own versions of dependencies. This make usre no external dependencies interfere with our application and that same explicit dependency package is consistently applied across all developments, stafing and production env. 

Out side of python capabilities like $curl and other dependency, we might need to go on with more of universal approach that works across all the different programming languages can help. Such as Docker containers. Docker allows us to run application in a self-container environemnt that is isolated from the host system. It is more effenciet and reliable way to manage dependencies. Here is simple example:

    FROM python:3.10-alpine

    WORKDIR /kodekloud-twelve-factor-app

    COPY requirements.txt /kodekloud-twelve-factor-app

    RUN pip install -r requirements.txt --no-cache-dir

    COPY . /kodekloud-twelve-factor-app

    CMD python app.py

From the first line here create an impage from the python base image then set the right working directory then copies the requirements or txt file to the working directory and then installs the dependencies and the copies the application code into the image and finally defines the command to run the application using the CMD instruction. Now by runing the "$ docker build..." command, we build an image and by running the "$docker run..." command. we run one instance of our application. 