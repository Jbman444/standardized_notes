### Basics of navigating the terminal and making the most of BASH


### Source of Notes and Link 


### check the version 

```bash
bash --version
```

### for mac use brew install bash
### for windows either use wsl or install git bash


## Basic Terminal Commands 
```bash
ls # List directory contents
cd # Change the current directory
pwd # Print the current working directory
echo # Display a line of text
cat # Concatenate and display files
cp # Copy files and directories
mv # Move or rename files
rm # Delete files or folders
touch # Create an empty file or update its time
mkdir # Create a new folder
du # file size
```

### If you see a command you are note familar with use --help to get details on how it works and what flags are available

---

# ls command - list directory contents

```bash
ls -a 
```
### list all the files in the directory. The -a flag tells the terminal you want to see the hidden files too. 



```bash
ls -l # Long listing format
ls -a # Include hidden files
ls -h # Human-readable sizes
ls -t # Sort by modification time
ls -r # Reverse order while sorting
ls -R # List subdirectories recursively
ls -S # Sort by file size
ls -1 # List one file per line
ls -d # List directories themselves, not their contents
ls -F # Append indicator (one of */=@|) to entries
```


### hidden files start with .


# Useful Commands

```bash
du -sh filename # shows you how much space is this file or directory
```
### What the flags mean
-h, --human-readable  print sizes in human readable format (e.g., 1K 234M 2G)

-s, --summarize       display only a total for each argument


### Check Permissions and size
```bash
ls -lh filename
```
### give a file the permission to run
```bash
chmod +x filename
```


### cd changing directory 

```bash 
cd .. # going back a directory
cd ../.. # going back two directories
cd ~ # going home
cd - # go back to your last directory
cd / # root of the file system
cd ~ && ls # combine change directory with another command
```

## pwd current directory 

```bash
pwd # gives you the current directory
```

Pro tip: you'll need to use the address of your current directory pretty often

### Make a new function using alias

```bash 

nano ~/.bashrc
# add the botttom of the bashrc file 
# alias copypwd='pwd | xclip -selection clipboard' # add this line
alias copypwd='printf "%s" "$PWD" | xclip -selection clipboard'
source ~/.bashrc
```
```bash
copypwd # new function will copy the current directory to your clipboard
```


### What is a shebang and how to run your scripts from the terminal

```bash
#!/bin/bash
echo "Starting the script..."
# Your script commands here
echo "Script finished."
```


```python
#!/usr/bin/env python3
```

### running the script
either you can explictly run it using bash 
```bash
bash filename
```
or you can use ./
```bash
./filename
```
this is the same for python
```bash
python3 filename
```
need to add the shebang to make sure the terminal knows what interpreter it should use
### Need to give permission to the filename so it can be executable
```bash
chmod +x filename # gives the file permission to execute
chmod -x filename # can remove permission to execute
```
# echo used to print out a string in the terminal
```bash
echo "echo is like print in python"
```

## cat can display the contents of a file and to combine mutiple files

### append the contents of one text file to another and save it as a new file 

```bash
# print file text out from the terminal
cat file1.sh

# pass text from a file to another function
cat file1.sh | grep "bash"

# append contents from one file to another and make a new file
cat file1.sh file2.sh > file3.sh
```

### flags available for cat
``` bash
cat -n # Add numbers to each line
cat -b # Add numbers only to lines with text
cat -s # Remove extra empty lines
cat -v # Show non-printing characters (except for tabs and end of line)
```


# cp copy files and directorys

```bash
# make a copy of a file with a new name
cp my_file.txt copy_of_my_file.txt

```
### Available flags 
```bash
cp -r # Copy all files and folders inside a directory
cp -i # Ask before replacing files
cp -u # Copy only if the source is newer
cp -v # Verbose mode, show files being copied
```
### Copying mutiple files of the same similar name or file type
```bash
# copy all text files to the following directory 
cp *.txt /destination/ 
```

# mv used to move or rename files 

```bash
# move file to new destination
mv filename /path/newfiledestination/
# renaming file
mv filename_old filename_new
```

### Available flags
```bash
mv -i # Ask before replacing files
mv -u # Move only if the source is newer
mv -v # Verbose mode, show files being moved
```

# rm deleting files

```bash
# deleting a file
rm filename.txt
# deleting a directory
rm -r directory/
```

## Available flags
```bash 
rm -r # Delete a folder and everything inside it
rm -i # Ask before deleting each file
rm -f # Force delete without asking
rm -v # Verbose mode, show files being removed
```
# mkdir make a new directory

```bash
mkdir directory_name
```
### Available flags
```bash
mkdir -p # Create parent directories as needed
mkdir -v # Show a message for each created directory
mkdir -m # Set file mode (permissions)
```

# man user manual for a given command

```bash
man mkdir # details of available flags and how to use command
```

# alias create a shortcut with a user def term

```bash
alias # list out all available 
```


```bash
alias gs='git status' # set the temporary alias for your terminal session
```
## If you want to set it for every terminal session

```bash
nano ~/.bashrc
# manually add the following line to the bottom of bashrc
alias gs='git status' # shorten command git status to gs
```
## shortcut to adding alias to the bashrc

### important note
# important note 
```bash
>> means append
> means replace
# if you use > instead of >> you will delete your bashrc
```

```bash
# the following line will add a new alias to the end of your bashrc
echo "alias gs='git status" >> ~/.bashrc
```
alias will be recognized at the start of every new terminal session
