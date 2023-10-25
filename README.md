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

### Change file permissions

In this task, you must determine whether any files have incorrect permissions and then change the permissions as needed. This action will remove unauthorized access and strengthen security on the system.
None of the files should allow the other users to write to files.
1.	Check whether any files in the projects directory have **write** permissions for the owner type of other. 
-	From the figure shown above, we can see the project_k.txt has write permissions for others.
2.	Change the permissions of the file identified in the previous step so that the owner type of other doesn’t have write permissions.
![https://i.imgur.com/CELySdN.png](https://i.imgur.com/CELySdN.png)
From the image above, we have determined that the file project_k.txt has write permissions for other. We are going to remove the write permissions using the **chmod** command.

**chmod o-w project_k.txt**
![https://i.imgur.com/PpAYBeN.png](https://i.imgur.com/PpAYBeN.png)
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The chmod command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the project_k.txt file. After this, I used ls -la to review the updates I made.

3.	The file project_m.txt is a restricted file and should not be readable or writable by the group or other; only the user should have these permissions on this file. List the contents and permissions of the current directory and check if the group has read or write permissions.
4.	Use the chmod command to change permissions of the project_m.txt file so that the group doesn’t have read or write permissions.

**chmod g-r project_m.txt **
