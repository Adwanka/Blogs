---
title: "📚 File Permissions and Access Control Lists"
datePublished: Fri Nov 17 2023 15:43:24 GMT+0000 (Coordinated Universal Time)
cuid: clp2shz2x000209jr65bk84yn
slug: file-permissions-and-access-control-lists
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700227591774/73d49d43-7ac3-4ffa-9c41-1228ddeb1c43.jpeg
tags: aws, devops, file-permission, shubhamlondhe, 90daysofdevops-chanllenge

---

## **DevOps 90-Days Challenge, Day-06**

---

### INTRODUCTION -

🔐Consider your computer as a vault with many rooms, each holding important data. Imagine now that each area is controlled by a complex key system, similar to 📁\*\*<mark>file permissions and Access Control Lists (ACLs)</mark>\*\* in the digital realm. Who can enter, see, alter, or even breathe close to these data rooms is determined by these "keys." We will solve the puzzles surrounding these digital guardians—file permissions and ACLs—in today's exploration. <mark>We'll figure out how they protect your virtual "rooms," manage who has access, and guarantee the integrity and confidentiality of your data.</mark> Prepare yourself for an engaging exploration of the fascinating realm of digital access control, from comprehending the fundamentals of access rights to deciphering the complex control provided by ACLs!

---

### File and Directory Permission Operations -

| Option | Execution |
| --- | --- |
| **<mark>+</mark>** | <mark>Adds a permission.</mark> |
| **<mark>_</mark>** | <mark>Removes a permission.</mark> |
| **<mark>=</mark>** | <mark>Assigns entire set of permissions.</mark> |
| **<mark>r</mark>** 📖 | <mark>Sets read permission for a file or directory.</mark> A file can be displayed or printed. A directory can have the list of its files displayed. |
| **<mark>w </mark>** 📝 | <mark>Sets write permission for a file or directory. </mark> A file can be edited or erased. A directory can be removed. |
| **<mark>x</mark>** ⚙️ | <mark>Sets execute permission for a file or directory</mark>. If the file is a shell script, it can be executed as a program. A directory can be changed to and entered. |
| **<mark>u</mark>** | <mark>Sets Permission for user who created and owns the file or directory.</mark> |
| **<mark>g</mark>** | <mark>Sets permissions for group access to a file or directory</mark>. |
| **<mark>o</mark>** | <mark>Sets permissions for access to a file or directory by all other users on the systems.</mark> |
| **<mark>a</mark>** | <mark>Sets permissions for access by the owner, group and all other users</mark>. |
| **<mark>s</mark>** | <mark>Sets User ID and Group ID permission; program owned by owner and group.</mark> |
| **<mark>t</mark>** | <mark>Sets Sticky bit permission; program remains in memory.</mark> |

| **Command** | Execution |
| --- | --- |
| **<mark>chmod</mark>** | <mark>Changes the permission of a file or directory.</mark> |
| **<mark>chgrp</mark>** <mark> groupname filename</mark> | <mark>Changes the group for a file or files</mark>. |
| **<mark>ls -l</mark>** <mark> filename</mark> | <mark>Lists a filename with its permission displayed.</mark> |
| **<mark>ls -ld </mark>** <mark>directory</mark> | <mark>Lists a directory name with its permissions displayed.</mark> |
| **<mark>ls -l</mark>** | <mark>Lists all files in a directory with its permission displayed.</mark> |

### Many people feel that setting permissions using numbers rather than letters is simpler.

### The binary representation of the numbers is as follows:

* `r`: Read permission 📖
    
* `w`: Write permission 📝
    
* `x`: Execute permission ⚙️
    

| RESULTING PERMISSION | RESULTING PERMISSION | RESULTING PERMISSION | NUMBERING |
| --- | --- | --- | --- |
| **4** | **2** | **1** | **7** |
| **r** | **w** | **x** | **7** |
| **r** | **w** | **\-** | **6** |
| **r** | **\-** | **x** | **5** |
| **r** | **\-** | **\-** | **4** |
| **\-** | **w** | **x** | **3** |
| **\-** | **w** | **\-** | **2** |
| **\-** | **\-** | **x** | **1** |
| **\-** | **\-** | **\-** | **0** |

***1)Limiting User Access to Files and Directory -***

A file or directory may have read, write,and execute permissions. When a file is created, it is automatically given read and write permissions for the owner, enabling you to display and modify the file. You may change these permissions to any combination you want. A file can also have read-only permission, preventing any modifications.

Three different categories of users can have access to a file or directory the owner, the group and all others not belonging to that group. The owner is the user who created the file. Any file you create, you own. You can also permit a group to have access to a file. In this case every other that file In this sense, every other user on the system makes up the others category.

**<mark>chmod</mark>** -

The **<mark>chmod</mark>** program allows you to modify various permission settings. It accepts two lists as inputs: filenames and permission changes. There are two ways in which you can specify the permissions list. The <mark>symbolic technique</mark> is one approach that makes use of permission symbols. Another approach is referred to as the <mark>numbering technique.</mark>

Example

**command** - **chmod 765 notes.txt/(note- add dir name)** - numeric technique

**chmod u+rwx g+rw o+rx notes.txt/(note -add dir name) -** symbolic technique

**The chmod change permissions of file as -**

**<mark>Owner has the permissions to read, write, and execute for users, groups, and others. For others, their rights are read and x-execute.</mark>**

***2) Modifying the Owner or Group of a File/ Directory:***

**<mark>chown</mark>**

Only the owner has the ability to modify a file's or dir permissions, even though other users might be able to access it. On the other hand, you can change the owner of the file or dir from yourself to another user if you wish to grant them power over any of the permissions on your file or dir. A file/dir can be turned over to another user with the **chown** command. The other user's name is the first argument this command accepts.

Example - **"chown"** is used to change the ownership permission of a file or directory

**command - chown** courseTWS notes.txt

**<mark>The chown change the ownership of file note.txt from ubuntu to courseTWS</mark>**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700232991418/7bc5bd2e-af58-4465-9265-ae2fd3e4f888.png align="center")

**<mark>chgrp</mark>** -

The **chgrp** command can also be used to modify a file's group, if desired. The name of the new group for a file or files is the first input that **chgrp** receives. You list the files you want moved to that group after the new group name.

Example - **<mark>"chgrp"</mark>** <mark> is used to change the group permission of a file or directory.</mark>

**command - chgrp DAy1 notes.txt**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700233556189/8587dec5-b066-4929-bffa-92f63799448c.png align="center")

---

### Access Control List (ACL) -

**Access Control Lists (ACL)** allow users to give more precise control over their files and directories.

The acl option must be used when mounting file systems. To set permissions, use the setfacl and getfacl commands found in the ACL tools (acl package).

<mark>The user, owner, and group permissions can be listed using the getfacl command.</mark>

<mark>The read, write, and execute permissions can be set with the setfacl to restrict access for particular users.</mark>

**command -**

**getfacl users &lt;name of directory / file&gt;**

**setfacl -m u:shub:rwx /de - permission of user**

**setfacl -m g:test:rwx /devops - permissoin to group**

**setfacl -b /devops - to remove all permission**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700235276249/0c2f659a-23b7-48e2-b3f5-9497c297ff05.png align="left")

---

### **CONCLUSION -**

*Emphasizing how crucial ACLs and file permissions are to preserving system security and allowing for the right kind of data access.*

**Kindly feel free to ask any queries in the section below. I'd be pleased to respond to them.**

**Please follow and use the heart❤❤ button below to express your support if you think this content is helpful 😊.**

**I appreciate you taking the time to read.**

@[Shubham Londhe](@TrainWithShubham) #90DaysofDevopschallenge #devops #Filepermissions#Cloud