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
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The **chmod** command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the project_k.txt file. After this, I used ls -la to review the updates I made.

3.	The file project_m.txt is a restricted file and should not be readable or writable by the group or other; only the user should have these permissions on this file. List the contents and permissions of the current directory and check if the group has read or write permissions.
4.	Use the chmod command to change permissions of the project_m.txt file so that the group doesn’t have read or write permissions.

**chmod g-r project_m.txt**

### Change file permissions on a hidden file

In this task, you must determine if a hidden file has incorrect permissions and then change the permissions as needed. This action will further remove unauthorized access and strengthen security on the system.

The file .project_x.txt is a hidden file that has been archived and should not be written to by anyone. (The user and group should still be able to read this file.)

1.	Check the permissions of the hidden file .project_x.txt and answer the question that follows.

![https://i.imgur.com/y2Osrij.png](https://i.imgur.com/y2Osrij.png)

2.	Change the permissions of the file .project_x.txt so that both the user and the group can read, but not write to, the file.

**chmod ug-w .project_x.txt**
**chmod g+r .project_x.txt**

![https://i.imgur.com/c6l1So4.png](https://i.imgur.com/c6l1So4.png)

### Change directory permissions

In this task, you must change the permissions of a directory. First, you’ll check the group permissions of the /home/researcher2/projects/drafts directory and then modify the permissions as required. (You should be in the projects directory while managing the permissions of its subdirectory drafts.)
Only the researcher2 user should be allowed to access the drafts directory and its contents. (This means that only researcher2 should have execute privileges.)
1.	Check the permissions of the drafts directory and answer the following question.
2.	Remove the execute permission for the group from the drafts directory.
**chmod g-x drafts**
![https://i.imgur.com/QjYuh6J.png](https://i.imgur.com/QjYuh6J.png)

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I previously determined that the group had execute permissions, so I used the chmod command to remove them. The researcher2 user already had execute permissions, so they did not need to be added.

### Summary

I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the projects directory. The first step in this was using ls -la to check the permissions for the directory. This informed my decisions in the following steps. I then used the chmod command multiple times to change the permissions on files and directories.


