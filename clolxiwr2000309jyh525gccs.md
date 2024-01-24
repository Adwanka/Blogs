---
title: "🚀 Advanced Linux Shell Scripting for DevOps Engineers with User management"
datePublished: Sun Nov 05 2023 20:32:01 GMT+0000 (Coordinated Universal Time)
cuid: clolxiwr2000309jyh525gccs
slug: advanced-linux-shell-scripting-for-devops-engineers-with-user-management
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699109951782/2fab7875-6a55-4fd6-bbc3-50adc43755fd.jpeg
tags: linux, aws, devops, shell-scripting, 90daysofdevops-chanllenge

---

## **DevOps 90-Days Challenge, Day-05**

---

### INTRODUCTION -

---

Your shell scripting abilities will advance with the help of the Advanced Scripting Techniques in this blog. We'll go over more complex methods including processing command-line parameters, redirecting output, and accepting user input. additionally, Utilize regular expressions' power to manipulate text in complex ways. additionally, Organize files and directories, verify the existence of files, and gracefully manage mistakes.

Before we dive into the script, make sure you have a basic understanding of the Bash shell and how to navigate the file system in your operating system.

---

## Tasks

---

1 **You have to do the same using Shell Script i.e using either Loops or command with start day and end day variables using arguments -**

**So Write a bash script create**[**directories. sh**](http://directories.sh) **that when the script is executed with three given arguments (one is the directory name and second is start number of directories and third is the end number of directories ) it creates a specified number of directories with a dynamic directory name.**

**Example 1: When the script is executed as**

`./`[`createDirectories.sh`](http://createDirectories.sh) `day 1 90`

**then it creates 90 directories as** `day1 day2 day3 .... day90`

---

**The purpose of this Bash script is to generate several dynamically named directories.**

\-A shebang is the first line that instructs the system to run the script using the Bash shell: **#!/bin/bash**.

\-After that, the path variable is set to **"/home/ubuntu."** This is the directory creation location that we want to use.

\-A directory called **"task\_one"** is created within the given path by the line

**mkdir** **$path/task\_one**. The parent directory for the group of directories we wish to make is this one.

**$1 — First argument**

**$2 — Second argument**

**$3 — Third argument**

\-It verifies that the right amount of arguments—three—are supplied. If not, it ends with a use notice. It verifies that the numbers at the beginning and finish are real integers. If not, it gives an error message before shutting down.

\-Lastly, the script makes several directories inside the **"task\_one"** directory using a for loop. By iterating from the start number to the finish number, it accomplishes this. The loop variable i is used to determining the current value of a new directory that is created for each iteration of the loop by combining the base name supplied as the first argument **($1)** with the current value of **i**, using the **mkdir** command. Up to the given end number, this creates directories with names like **"day 1," "day 2,"** and so forth.

\-The script indicates the range of directories that path where the directories are created.

\-Before executing the script, ensure it has executable permissions. If not, grant the necessary permissions using **#chmod 700 createdirectories. sh**

\-To run the script, execute it in your terminal: **./createdirectories. sh**

```bash
#!/bin/bash 
path-/home/ubuntu/task1
mkdir $path/task_one
for (( i=$2; i<$3; i++ ))
do
    mkdir $path/task_one/$1$i
done
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699116422153/d95b44e2-5fe0-49f4-8f09-593d037e35cc.png align="center")

---

**2 Create a Script to backup all your work done till now.Backups are an important part of DevOps Engineer's day-to-day activities.**

---

**Let's deconstruct the supplied backup script using straightforward terminology.**

* A shebang is the first line that instructs the system to run the script using the Bash shell: #!/bin/bash.
    
* we designate the location for our backup storage. The exact location on your computer where you want to store your backups should be used in place of "/path/to/backup". Your backed-up data will be stored here.
    
* To confirm that the backup directory exists, we run the **mkdir** command. Should it fail to do so, the script will generate it on your behalf. This is similar to ensuring sure your backup files are ready to be stored in a folder.
    
* Finally, we show you a message to let you know that the backup was created. This message tells you where your backup "box" (the archive) is stored. So, if you ever need to access your old work, you can find it in this location.
    
* In simple terms, this script takes all your work, puts it in a "box," and then stores that "box" in a safe place so you can retrieve it later if you need to. It's like making a copy of your important documents and keeping them in a secure drawer in case you ever want to use them again. This way, you won't lose your hard work.
    
* Before executing the script, ensure it has executable permissions. If not, grant the necessary permissions using **#chmod 700 backupscript. sh**
    
* To run the script, execute it in your terminal: **./backupscript. sh/**
    
    ```bash
    #!/bin/bash
    
    # Define the backup directory
    backup_dir="/path/to/backup"
    
    # Create the backup directory if it doesn't exist
    mkdir -p $backup_dir
    
    # Archive the work directory and compress it
    timestamp=$(date +'%Y%m%d_%H%M%S')
    backup_filename="backup_${timestamp}.tar.gz"
    
    tar czf "${backup_dir}/${backup_filename}" /path/to/your/work/directory
    
    echo "Backup created: ${backup_dir}/${backup_filename}"
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699125087946/1673a323-039f-4a92-975a-b4dba59a605e.png align="right")

---

**3 Read About Cron and Crontab, to automate the backup Script**

---

**Corn**

Linux servers use **cron** services to plan regular maintenance tasks including backups, alarm clocks, and updates carried out by a cron daemon.

In Unix and Linux systems, the word **"daemon"** is frequently used to refer to background programs that carry out different system functions.

When it comes to **cron**, the background process in charge of automating the execution of scheduled tasks by crontab configurations is known as the **cron daemon**. It guarantees that these actions are completed at the designated times without requiring users to manually intervene.

It functions as follows:

1. **Cron Configuration**:
    
    Users can designate which tasks they want to perform at what time by using a file called a "crontab." Entries in the crontab include details about the task or script to be run as well as the schedule such as time and frequency.
    
2. **Cron Daemon**:
    
    The cron daemon is a system service that continuously monitors the crontab files. It checks the current time and matches it with the scheduled times specified in the crontab entries.
    
3. **Task Execution**:
    
    When the specified time or condition is met, the cron daemon launches the associated task or command as a separate process. These tasks run in the background, often with limited user interaction.
    
4. **Logging**:
    
    The cron daemon typically records the output and results of these tasks in log files, so users can review the execution history and diagnose any issues
    

***Let's use the following as an example to clarify:***

**Backup:**

It's essential to regularly backup your critical files. You intend to make a daily midnight backup of your files. This may be automated with cron, which allows you to set up a backup job to run every day at midnight. Either an external device or cloud storage can be used to copy your stuff.

**Step 1: Create a Backup Script**

Create a backup script, for example, "[backupData.sh](http://backup.sh)," that copies your important files to an external drive or cloud storage.

**source\_directory** -The desired place for keeping a backup

**target\_directory -** the file where the data is to be taken as a backup

You can use the **rsync** command, which is a common choice for file synchronization and backup tasks.

```plaintext
#!/bin/bash

# Define source and target directories
source_directory="home/ubuntu/backups"
target_directory="home/ubuntu/shellscripts"

# Perform the backup using rsync
rsync -av --delete "$source_directory" "$target_directory"
```

Save this script to a location accessible by your user

and make it executable by running **chmod +x** [**backupData.sh**](http://backup.sh)**.**

**Step 2: Schedule the Backup with Cron**

Open your crontab for editing:

```bash
crontab -e
```

Add the following line to schedule your backup script to run at midnight every day:

```bash
0 0 * * * "home/ubuntu/backups"-
| | | | |
| | | | +--------***DAY OF WEEK***(0-6)
| | | +--------***MONTH***(1-12)
| | +------***DAY OF MONTH***(1-31)
| +-------***HOUR***(0-23)
+----**MINUTE**(0-59)
```

* `0` in the first position represents midnight (the hour).
    
* `0` in the second position represents the first minute of the hour.
    
* `*` positions means "every day of the month"
    
* `*` positions means "every month"
    
* `*` every day of the week.
    
    Save your crontab and exit your text editor
    

**Alarm Clock:**

With cron jobs, you may use Linux to automate actions such as launching work apps, putting on your favorite morning music, and turning on the coffee maker. To replicate your everyday morning routine, you can construct a basic set of cron tasks like the following:

**Step 1: Create Shell Scripts**

Create two shell scripts for each task you want to automate:

1. `play_song.sh` - This script plays your favorite morning song.
    
2. `start_work_apps.sh` - This script opens your work applications.
    

Here are basic examples of what these scripts might look like:

```bash
# play_song.sh
#!/bin/bash 
/home/ubuntu/corneg/Music/morning_song.mp3
```

```bash
# start_coffee_maker.sh
#!/bin/bash
firefox
```

Make sure to make these scripts executable by running

chmod 700 play\_song.sh start\_coffee\_maker.sh

**Step 2: Schedule Tasks with Cron**

Next, you can schedule these scripts to run automatically at the times you specified in your morning routine.

Open your crontab for editing:

```bash
crontab -e
```

Now, add the following lines to your crontab file to schedule the tasks:

```bash
#!/bin/bash
# Play your favorite morning song at 7 AM
0 7 * * * /home/ubuntu/corneg/play_song.sh
```

```bash
#!/bin/bash
# Open work applications at 8 AM
0 8 * * *  /home/ubuntu/corneg/start_work_apps.sh
```

Save your crontab and exit your text editor

---

**4 Read about User Management.**

---

In a system running Linux or Unix, managing user accounts includes creating, editing, and deleting them. Making sure users can access and use system resources securely is an important element of system administration.

1. **Creating Users:**
    
    To create a new user account, you use commands like `useradd` or tools like `adduser` (Debian/Ubuntu) or `useradd` (Red Hat/CentOS). You specify the username, user ID (UID), home directory, and other parameters.
    
2. **Setting User Passwords:**
    
    After creating a user, you use the `passwd` command to set a password for the user. Password policies can be enforced, including password complexity requirements and expiration policies.
    
3. **User Information:**
    
    You can set additional user information like full name, phone number, and comments using the `usermod` command with the `-c` option. User information is stored in the `/etc/passwd` file.
    
4. **User Groups:**
    
    Users can belong to one or more user groups, which determine their access to resources and permissions. You can add users to existing groups or create new groups using the `groupadd` and `usermod` commands.
    
5. **Modifying Users:**
    
    You can modify user attributes like the home directory, login shell, and group membership using the `usermod` command. For example, to change a user's default shell, you can use `usermod -s /bin/bash username`.
    
6. **Locking and Unlocking Users:**
    
    To temporarily prevent a user from logging in, you can use the `passwd` command with the `-l` option to lock their account. To unlock it, use `passwd -u`.
    
7. **Deleting Users:**
    
    Use the `userdel` command to delete a user account. You can also remove the user's home directory and mailbox by using the `-r` option: `userdel -r username`.
    
8. **User Privileges:**
    
    Some systems allow user privileges to be elevated through group memberships, such as the "sudo" group. Members of the "sudo" group can execute administrative commands with superuser privileges using `sudo`.
    
9. **User Authentication:**
    
    User authentication can be managed through different methods, including password-based, SSH keys, or biometrics. Configuration for these methods is done in various files like `/etc/passwd`, `/etc/shadow`, and `/etc/ssh/sshd_config`.
    
10. **User Monitoring:**
    
    System administrators may monitor user activities through log files, auditing tools, and security policies to ensure system security and compliance.
    
11. **User Quotas:**
    
    User quotas can be set for file systems to limit the amount of disk space a user can consume. Tools like `quota` and `edquota` can be used to manage these quotas.
    

**Password Policies:**

Systems often enforce password policies that specify password complexity, length, and expiration rules. These policies are managed through the `/etc/security` directory or similar configuration files.

<details data-node-type="hn-details-summary"><summary></summary><div data-type="detailsContent">Effective user management is essential for maintaining the security and efficiency of a Linux system. It helps control access to resources, manage system resources, and ensure compliance with security policies.</div></details>

---

**5 Create 2 users and just display their Usernames**

---

There are other commands in Linux that you may use to add a user, but **useradd** is one of the more popular ones. The **useradd** command can be used to add a new user in the following ways

1. To add a new user, run the following command,
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699215001026/10144b18-9e8d-4c16-8baf-8e0a0f763a89.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699215027744/04b953bd-668f-4523-9088-2f7badfffed5.png align="center")

1. By default, the `useradd` command only creates a new user account. To set a password for the new user, use the `passwd` command:
    

```bash

sudo passwd newuser
```

3 you can add additional information to the user's account, such as full name, phone number, and more, using the `usermod` command. For example:

phone number, and more, using the `usermod` command. For example:

```bash
 sudo usermod -c "John Doe" -m -s /bin/bash -G sudo newuser
```

* `-c "John Doe"` sets the user's full name.
    
* `-m` creates the user's home directory.
    
* `-s /bin/bash` sets the user's default shell to Bash.
    
* `-G sudo` adds the user to the "sudo" group, giving them administrative privileges.
    

---

### CONCLUSION -

---

> Day 5's focus on user management in advanced Linux shell scripting is crucial for DevOps engineers. It equips them with the knowledge and skills to manage user accounts effectively, maintain system security, and ensure smooth operations in their Linux environments. With these skills, DevOps engineers can create and maintain user accounts, configure access controls, and implement security policies to meet the demands of their organizations.

**Kindly feel free to ask any queries in the section below. I'd be pleased to respond to them.**

**Please follow and use the heart❤❤ button below to express your support if you think this content is helpful 😊.**

**I appreciate you taking the time to read.**

@[Shubham Londhe](@TrainWithShubham)