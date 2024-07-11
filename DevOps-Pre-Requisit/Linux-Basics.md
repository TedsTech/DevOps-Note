# Basic Commands

## Print to screen
````bash
echo Hi  
 ````
 Output
 ````bash
Hi  
 ````
## List Files & Folders
````bash
ls
````
 Output
 ````bash
 File.txt, my_dir1, file2.conf
````
## Change directory
````bash
cd my_dir1
````
## Present Working Directory
````bash
pwd
````
Output
````bash
/home/my_dir1
````
## Make Directory
````bash
mkdir new_directory
````
## Multiple commands
````bash
cd new_directory; mkdir www; pwd
````
Output
````bash
/home/my_dir1/new_directory
````

# Commands - Directories

## Make Directory Hierarchy
````bash
mkdir -p /tmp/asia/nepal/jhapa
````
## Remove Directory
````bash
rm -r /tmp/my_dir1
````
## Copy Directory
````bash
cp -r my_dir1 /tmp/my_dir1
````

# Commands - Files

## Create a new file (no contents)
````bash
touch new_file.txt
````
## Add contents to file
````bash
cat > new_file.txt
This is some simple contents
and press CTLR + D when you're done
````
## View contents of file
````bash
cat new_file.txt
````
## Copy File
````bash
cp new_file.txt copy_file.txt
````
## Move (Rename) File
````bash
mv new_file.txt sample_file.txt
````
## Remove (Delete) File
````bash
rm new_file.txt
````

# User Account

## Display the current user
````bash
whoami
````
## Find user & group name
````bash
id
````
## Switch user
````bash
su David
````
## Connect to a remote server
````bash
ssh david@192.168.1.2
````
## Root directory
````bash
ls /root
````
## Directory with root permission
````bash
sudo ls /root
````

# Download Files

````bash
curl http://www.some-site.com/some-file.txt -0
````

````bash
wget http://www.some-site.com/some-file.txt -0 some-file.txt
````

# Check OS Version

````bash
ls /etc/*release*
````

````bash
cat /etc/*release*
````

# Package Managers

## RPM (Red Hat Package Manager)

Install Package
````bash
rpm -i telnet.rpm
````

Uninstall Package
````bash
rpm -e telnet
````

Query Package
````bash
rpm -q telnet
````

## YUM

Install Package
````bash
yum install ansible
````

YUM Repos
````bash
yum repolist
````

Show YUM file
````bash
ls /etc/yum.repos.d/
````

YUM list for specific package
````bash
yum list ansible
````

To remove and installed package
````bash
yum remove ansible
````

To show Duplicate option
````bash
yum --showduplicates list ansible
````

To install a specific version
````bash
yum install ansible-2.4.2.0
````

# Services

## Start HTTPD service
````bash
service httpd start
````
or 
````bash
systemctl start httpd
````
## Stop HTTPD Service
````bash
systemctl stop httpd
````
## Check HTTPD Service Status
````bash
systemctl status httpd
````
## Configure HTTPD to start at startup
````bash
systemctl enable httpd
````
## Configure HTTPD to not start at startup
````bash
systemctl disable httpd
````

# Example of some Exec Service

```
thor@host01 ~$ sudo systemctl cat app.service
# /usr/lib/systemd/system/app.service
[Unit]
Description=My python web application

[Service]
ExecStart=/usr/bin/python3 /opt/code/my_app.py
ExecStartPre=/bin/bash /opt/code/configure_db.sh
ExecStartPost=/bin/bash /opt/code/email_status.sh
Restart=always

[Install]
WantedBy=multi-user.target
```
