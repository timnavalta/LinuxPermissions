# File Permissions in Linux

### Project Description
This project is to exercise and confidently put to usage some Linux commands for managing file permissions. Understanding file permissions in Linux is crucial for cybersecurity professionals because it forms the foundation of access control and security on Linux systems. The research team at my organization needs to update the file permissions for certain files and directories within the projects directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure.

### Check file and directory details
In this task, you must explore the permissions of the **projects** directory and the files it contains. The lab starts with **/home/researcher2** as the current working directory. This is because you're changing permissions for files and directories belonging to the researcher2 user.

1.	Navigate to the projects directory.
2.	List the contents and permissions of the projects directory.

Typing **ls –al** allows us to display the list of names and features of files and directories in the current directory.
The ls command is one of the more basic commands in Linux. It is designed to list the names of files and directories. With the –al argument, -a lists all files including those that begin with . and l do not list implied entries matching shell PATTERN.

Now using the results in the figure, it shows different names of users and groups as well as their respective permissions.
(https://imgur.com/pS8JkaY)
