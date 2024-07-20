Install git package using yum on host01 server.

````bash
thor@host01 ~$ sudo yum install git
````

On host01 create/initialize a git repository myrepo in thor user's home directory.

````bash
thor@host01 ~$ cd /home/thor
thor@host01 ~$ git init myrepo
````

Add the index.html file to the git repo so it's changes are tracked. And then commit the changes. Use any message while committing.

````bash
thor@host01 ~/myrepo$ git add index.html
thor@host01 ~/myrepo$ git commit -m "tracking file"
    [master 64be428] tracking file
     1 file changed, 1 insertion(+)
     create mode 100644 index.html
````

Which of the following command is used to download a remote git repository to local for the first time?

````bash
git clone
````

Which of the following command should be used to update the local repository with all changes from the repository?

````bash
git pull
````

Which command you will use to upload your changes to a remote git repository?

````bash
git push
````

What is default name for the first remote for a git repository?

````bash
origin
````

On host01 clone a git repository https://github.com/kodekloudhub/webapp-color.git in thor user's home directory.

The git repository should be available at /home/thor/webapp-color

````bash
git clone https://github.com/kodekloudhub/webapp-color.git
````

Remote repositories need not always be on remote servers. They can be located on the same server too. We have a remote repository on host01 at path /opt/remoterepo.git. Clone it to thor user's home directory.

The git repository should be available at /home/thor/remoterepo

````bash
thor@host01 ~$ cd /home/thor/
thor@host01 ~$ git clone /opt/remoterepo.git/
    Cloning into 'remoterepo'...
    warning: You appear to have cloned an empty repository.
    done.
````

In your cloned repository i.e /home/thor/remoterepo create a file index.html with content This is a sample file. Track the new file, commit the changes and finally push the same to remote repo in master branch.

````
thor@host01 ~$ pwd
/home/thor

thor@host01 ~$ cd remoterepo/

thor@host01 ~/remoterepo$ echo > index.html
thor@host01 ~/remoterepo$ ls
index.html

thor@host01 ~/remoterepo$ vi index.html 

thor@host01 ~/remoterepo$ cat index.html 
This is a sample file

thor@host01 ~/remoterepo$ git add index.html

thor@host01 ~/remoterepo$ git commit -m "update index file"
[master (root-commit) 55c7c51] update index file
 1 file changed, 1 insertion(+)
 create mode 100644 index.html

thor@host01 ~/remoterepo$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 233 bytes | 233.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To /opt/remoterepo.git/
 * [new branch]      master -> master
````