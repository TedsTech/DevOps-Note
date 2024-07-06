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
and press CTLR + D when your done
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