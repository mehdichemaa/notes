## The Rule of Least Privilege
One of the most important rules in security, is the rule of least privilege. This means, a user or an application only has enough permission to do its job. Nothing extra.

## Becoming a Super User
Every linux machine comes with the user named root. This user is super powerful. They can do anything they want on this machine.
**It's very common to disable the ability to remotely login as root.** Instead we will login as a user we create, and then can run individual commands as root by using another command. This is to make any potential attackers job a little more difficult, by eliminating the username that they already know existsn on this machine. 
This should be the very first thing you need to do when setting up a new server.
The `sudo` command is the one we use to execute commands as super user.

## sudo vs su
**It is NOT recommended to use the `su` command, due to the Rule of Least Privilege**.

## Package Source List
All the available Package Lists are listed in:
`cat /etc/apt/sources.list`
Every time you try to install or update a software, the system will reference this source list.
![Package Source List](https://linuxhint.com/wp-content/uploads/2018/09/2-11.png)
The listings are software repositories.

## Updating Available Package Lists
Most of Linux distros do not auto update software installed on the system. That is because Linux systems focus on reliability, and run a variaty of complex applications that have  numerous dependencies of their own. You need to this yourself, and test your apps, to make sure that the update did not break your app.

The first step to upgrading your installed software, is to first update your Package Source List. We do this using:
`sudo apt-get update`
This command does not actually upgrade your software. It just make sure that your system is aware of any news changes to the software repositories that your making use of. In other words, it updates the Package Source List with new software version numbers, links, etc.

## Upgrade Installed Packages
Now that we have information about the latest changes to the packages (software), we can now upgrade them. We do that using:
`sudo apt-get upgrade`
Doing so will show you a list of the packages that need to be upgraded, and most of them you won't know what they are, but you might be familiar with some of them. The shell will ask you if you approve the upgrade or not. **Make sure you do this in a dev environment to test your applications if they are still working**, because any of these changes can break you apps.

## Other Package Related Tasks
The command `apt-get` is your door to any package related tasks. The command `man apt-get` shows you all it can do. For example, `sudo apt-get autoremove` will remove any packages that are no longer necessary.

## Discoverin Packages
Each distribution tends to publish an easy to browse version of their repositories.

## Using Finger
This application, will look up various information about a user, and display it in an easy to read format. Using `finger` will output an information about all the user that are currently logged into the system. You can also user `finger username` to see more information about a specific user, such as home directory, and what shell they are using. 

## Introduction to /etc/passwd
The information about the user that `finger` is return is stored on a file called `/etc/passwd`. This file store information about each user. Each line of that file, is an entry for a single user, and each entry has a number of fields that are seperated by colons.
`/etc/passwd` file format is:
`Username:Password:User ID (UID):Group ID (GID):User ID Info (GECOS):Home directory:Command/shell`
For `Password`: an x character indicates that encrypted and salted password is stored in /etc/shadow file.
https://www.cyberciti.biz/faq/understanding-etcpasswd-file-format/