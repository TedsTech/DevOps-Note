# Install Apache Web Server

In CentOs, Apache is avilable within the default software repository.

## Install httpd
````Bash
yum install httpd
````

## Start the httpd
````Bash
service httpd start
````

## Verify the service is still running
````Bash
service httpd status
````

## To add a rull to allow HTTP traffic
````Bash
firewall-cmd --permanent --add-service=http
````

# View Logs

## To access the file
````Bash
cat /var/log/httpd/access_log
````

## To view the error log
````Bash
cat /var/log/httpd/error_log
````

# Config File

In Apache web server it's usually located at 

    /ect/httpd/conf/httpd.conf

## After update the conf file, Must restart the service
````Bash
service httpd restart
````
# Apache Web Server Lab

Install apache and start httpd process

````Bash
thor@host01 ~$ sudo yum install httpd

thor@host01 ~$ sudo systemctl start httpd

thor@host01 ~$ sudo systemctl status httpd
````

We have added dummy html files and some dependent images to /opt/food directory.Make sure that this content is available on apache page

````Bash
thor@host01 ~$ sudo mv /opt/food/* /var/www/html/
````