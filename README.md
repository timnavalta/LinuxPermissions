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
![https://i.imgur.com/pS8JkaY.png](https://i.imgur.com/pS8JkaY.png)

### Describe the permissions string

The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:
●	1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.
●	2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.
●	5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.
●	8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.

For example, the file permissions for project_t.txt are -rw-rw-r--. Since the first character is a hyphen (-), this indicates that project_t.txt is a file, not a directory. The second, fifth, and eighth characters are all r, which indicates that user, group, and other all have read permissions. The third and sixth characters are w, which indicates that only the user and group have write permissions. No one has execute permissions for project_t.txt.
![https://i.imgur.com/xJIzZXi.png](https://i.imgur.com/xJIzZXi.png)
