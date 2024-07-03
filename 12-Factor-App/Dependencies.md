Explicitly declare and isolate dependencies.

Let's start with the example so we can fully understand by the end of the course.

For example, we installed the Flask framework a Python web application framework before writing our code. Therefore it is essential to install the flask python framework in our local dev env before beginning the development. This is just one dependency of our Flask web application. But when we keep growing, we may have many third-party dependencies.
    $ pip install flask

    on app.py you will have "from flask import Flask"

The most important we need to remember is that "A twelve-factor app never relies on the implicit existence of system-wide packages. This means you cannot assume that the dependencies such as flask in this case will exist on the system where you will be running your app. So this rule in the 12-factor app recommends to explicity declare an isolated dependency. 

Many applications have multiple dependencies that must be installed before running the application. In the case of Python, these dependencies are typically listed in a file named requirments.txt in a specific format like this.
    file name: requirements.txt
        flask=2.0.0

It's important to know that each version number is specified after the package name. Without this, the different developers may install different versions leading to inconsistencies when the program is run in different environments. for example, when the dev runs into one version during development, and by the time it goes to production the operation team may install a different version without the dev knowing. This could cause the app to not function as expected. However in the end the pip install command will take care of all the dependencies listed in the requirements file during the build process. 

Now let's talk about isolating the dependencies which is the second part of this rule. 

Let's say we are working on developing two separate services or separate applications on our laptop and if one app requires one version of Flask and another requires another version. It is a best practice to create an isolated environment for our application that includes all the necessary dependencies. Different programming languages provide different approaches. For example, python has a concept of virtual environments(Venv). With Venv, we can create an isolated environment for each application with its versions of dependencies. This makes sure no external dependencies interfere with our application and that the same explicit dependency package is consistently applied across all developments, staging, and production environments. 

Outside of Python capabilities like $curl and other dependencies, we might need to go on with more of a universal approach that works across all the different programming languages. Such as Docker containers. Docker allows us to run applications in a self-contained environment that is isolated from the host system. It is a more efficient and reliable way to manage dependencies. Here is a simple example:

    FROM python:3.10-alpine

    WORKDIR /kodekloud-twelve-factor-app

    COPY requirements.txt /kodekloud-twelve-factor-app

    RUN pip install -r requirements.txt --no-cache-dir

    COPY . /kodekloud-twelve-factor-app

    CMD python app.py

From the first line here create an image from the Python base image set the right working directory copy the requirements or Txt file to the working directory and then install the dependencies that copy the application code into the image and finally define the command to run the application using the CMD instruction. Now by running the "$ docker build..." command, we build an image, and by running the "$docker run..." command. we run one instance of our application. 
