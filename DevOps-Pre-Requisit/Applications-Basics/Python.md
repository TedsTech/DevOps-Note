As per stack overflow insights , which two are most widely used web frameworks in Python?

    Diango, Flask

Clone python app repository from github in /opt/ directory.
Repo URL: https://github.com/mmumshad/simple-webapp-flask

````bash
thor@host01 ~$ cd /opt/

thor@host01 /opt$ pwd
    /opt

thor@host01 /opt$ sudo git clone https://github.com/mmumshad/simple-webapp-flask

Cloning into 'simple-webapp-flask'...
remote: Enumerating objects: 54, done.
remote: Counting objects: 100% (31/31), done.
remote: Compressing objects: 100% (16/16), done.
Receiving objects: 100% (54/54), 14.51 KiB | 14.51 MiB/s, done.
remote: Total 54 (delta 19), reused 21 (delta 15), pack-reused 23
Resolving deltas: 100% (22/22), done.
````

Install the requirements for app in /opt/simple-webapp-flask.
Requirements are in requirements.txt file.

````bash
thor@host01 /opt$ cd simple-webapp-flask/

thor@host01 /opt/simple-webapp-flask$ sudo pip install -r requirements.txt

verify the downloaded items by running 'sudo pip list'
````

Change port in app.py to 5000 and start the app.

````bash
thor@host01 /opt/simple-webapp-flask$ sudo sed -i 's/8080/5000/g' app.py
thor@host01 /opt/simple-webapp-flask$ sudo pip3 install flask
thor@host01 /opt/simple-webapp-flask$ python3 app.py
 * Serving Flask app 'app'
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5000
 * Running on http://172.16.238.3:5000
````

Now stop previously running app and run app.py with Gunicorn.

````bash
thor@host01 /opt/simple-webapp-flask$ sudo pip install gunicorn --upgrade
thor@host01 /opt/simple-webapp-flask$ gunicorn app:app
````

Run Gunicorn with 3 workers in background and confirm with curl command.

````bash
thor@host01 /opt/simple-webapp-flask$ nohup gunicorn app:app -w 3 &
[1] 3840
thor@host01 /opt/simple-webapp-flask$ nohup: ignoring input and appending output to '/home/thor/nohup.out'
curl localhost:8000
Welcome!thor@host01 /opt/simple-webapp-flask$ curl localhost:8000
````