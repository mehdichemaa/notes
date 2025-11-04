pwd: current working directory
cd: current directory
ls: list folders and files
ls -a: list all folders and files even the hidden ones
ls -al: list all folders and files even the hidden ones in long format (more details). 

When using the "ls -al" command, to differentiate between a directory and a file, chech the first character:
- If it's a "d", it is a directory
- If it's a "-", it's a file

## / 
The root level of the file system.

## home
The home directory hosts all the home directories of each user.

## etc
Is where the configuration files live. So, when setting up a web and database server, we will be modifying files within this directory.

## var
Var is a directory of variable files. Variable files are files that you expect to change in size over time. You typically find system and application logs in the directory.

## bin
Bin is where the executable binaries are stored, that are accessible by all users. These are applications you run, like the ls command command.

## sbin
sbin is like bin, but the binaries in it can only be used by the root user, for system administration, and maintance purposes.

## lib
lib is for libraries that support the binaries that are located around the system.

## usr
usr is for user programs. The difference between bin and usr is that the binaries in bin are required for system boot up and system maintainance processes. And the binaries in usr are not required for that.

## $PATH
Is a variable that stores paths to directories. So when run an app, the system will check first the $PATH and go through the directories to find it, and if it's not there, the app won't run.