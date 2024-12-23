# Permission Patrol Lab: Managing File Authorization in Linux

## Objective

In this lab, I worked on managing file permissions in Linux to ensure proper authorization for a research team. The activity involved examining existing permissions, identifying mismatches, and modifying them to secure the system by granting appropriate access and removing unauthorized users.



### Skills Learned

- Proficient in using Linux command-line tools to inspect and modify file permissions.
- Understanding of file ownership, groups, and permission types (read, write, execute).
- Ability to enforce the principle of least privilege by authorizing appropriate access and removing unauthorized users.
- Experience in managing user and group permissions to enhance system security.
- Analytical skills in assessing and rectifying mismatched file system permissions.



### Tools Used

- Linux Command Line: For navigating the file system and managing permissions.
- chmod: To modify file and directory permissions.
- ls -l: To inspect detailed file and directory permissions.

## Steps

![Screen Shot 2024-12-23 at 1 42 48 PM](https://github.com/user-attachments/assets/eb67e14c-043a-4928-beb0-a9872bdcdd5f)

Ref 1. This is the scenario that we are faced with in this specific lab

![Screen Shot 2024-12-23 at 1 47 36 PM](https://github.com/user-attachments/assets/0d0ad8fb-c6a3-4c33-a2fd-1223424f6441)

Ref 2. In this screenshot, I print the working directory using the pwd command to see what directory I am working in, then I ask Linux to list the subdirectories inside of the researcher2 directory using the ls command. I would like to check the permissionss set for files and subdirectories in the projects directory, so I use the cd command to navigate to the projects directory. Lastly, I use the ls -la command to inspect all detailed file and directory permissions including hidden ones. 

![Screen Shot 2024-12-23 at 1 53 34 PM](https://github.com/user-attachments/assets/d28aee6d-84ce-40f0-a08a-e6584fb0bbf1)

Ref 3. As an example, I use the output of the permissions for the hidden file .project_x.txt to break down the 10-character string. In this 10-character string, the 1st character indicatres the file type, because it is a hypen (-), it is a regular file not a directory. The 2nd-4th characters indicate the read, write, and execute permissions for the USER. This means in this output that the user only has permission to read and write to this file. The hyphen (-) indicates that the user is not allowed execution permissions. The 5th-7th characters indicate that the GROUP is not allowed read or execution permissions due to the hypens (-) in place. This means that the group only has writing permissions. The 8th-10th characters indicate the permissions for the owner type of OTHER. In this example, the owner type other has no permissions to read, write, or execute in the file.

![Screen Shot 2024-12-23 at 2 01 37 PM](https://github.com/user-attachments/assets/b5290668-daa6-4ffa-a0e9-9ed41ae8e508)
![Screen Shot 2024-12-23 at 2 02 36 PM](https://github.com/user-attachments/assets/d5cf2fb7-0217-4c1d-be02-98dda9c8148a)

Ref 4. As you can see in this example in this first screenshot for the file project_k.txt, the owner type other was granted permission to write to that file. In the second screenshot I used the command "chmod o-w project_k.txt" in order to remove the write permission from the owner type other. Then, I used the command ls -la again to display the detailed file and directory permissions. This resulted in the w being removed from the 10-character string specifically the 9th character.

![Screen Shot 2024-12-23 at 2 16 46 PM](https://github.com/user-attachments/assets/87df4d69-40dd-4a47-9eab-b730c9d8d79e)

Ref 5. The research team archived .project_x.txt which is why it is a hidden file. This file should not have write permissions fo ranyone, but the user and group should be able to read the file. This is a screenshot of the command I used "chmod u-w .project_x.txt" to removes writing permission for the user. 

![Screen Shot 2024-12-23 at 2 24 00 PM](https://github.com/user-attachments/assets/e747e279-f67b-403d-982a-9b0b2cac9e8f)

Ref 6. In this screenshot I use the "ls -la" command to display the changes made to the hidden file permissions. As you can see the user no longer has permission to write to the file.

![Screen Shot 2024-12-23 at 2 27 00 PM](https://github.com/user-attachments/assets/3ed848ec-96f6-4300-87ba-c292c877517c)

Ref 7. This screenshot shows me using the command "chmod g+r .project_x.txt" to add read permissions to the file for the GROUP owner type and the "ls -la" to display the new permissions for the hidden file which only allows users and group owner types to only be able to read, but not write to the file.

![Screen Shot 2024-12-23 at 2 34 03 PM](https://github.com/user-attachments/assets/caffbea6-6c97-463e-b24a-d7d2dcbae595)

![Screen Shot 2024-12-23 at 2 31 55 PM](https://github.com/user-attachments/assets/c5850363-a3d2-4f9f-8f13-feceae5e7f4e)

Ref 8. Lastly, in this screenshot the files and directories in the projects directory belong to the researcher2 user. Which measn only researcher2 should be allowed to access the drafts directory. As you can see in the first screenshot, the group owner type has permission to execute the file. I use the "chmod g-x drafts" command to remove the execution permission and display the changes made with "ls -la".





