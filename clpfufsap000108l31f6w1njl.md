---
title: "📦Understanding package manager and systemctl"
datePublished: Sun Nov 26 2023 18:58:42 GMT+0000 (Coordinated Universal Time)
cuid: clpfufsap000108l31f6w1njl
slug: understanding-package-manager-and-systemctl
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700807954099/1496e4a9-9d1b-41c0-a569-a56756635f9e.jpeg
tags: devops, package-manager, systemd, awscommunity, linux-for-beginners, service-manager, systemctl, shubhamlondhe, trainwithshubham, 90daysofdevops-chanllenge, day7-90daysofdevops, coloud

---

## **DevOps 90-Days Challenge, Day-07**

---

### OVERVIEW -

Today, we learned about package managers and how to manage Linux services. Since there are no prerequisites, it is best to log in as the root user and download the tools in RPM, DEB, and many more formats. Join us as we delve deeper into the intriguing world of Linux package management and service control, highlighting the differences that differentiate each distribution's unique approach and preparing you to use these skills in your automation world."

### ***What is a package manager in Linux?***

The package manager refers to any installed packages or applications that need to be managed, and it manages how to install them as well as how to remove or uninstall them once they are installed. How to verify package and configuration file information and how to update or upgrade to the latest versions All of these tasks are controlled and carried out by commands or tools.

**A package manager usually consists of the following:**

**Repository -**

A lot of software and documentation for your Linux distribution is available as packages in one or more centrally distributed repositories. These packages in such a repository are tested and very easy to install, update, and uninstall with a graphical or command-line installer.

**Dependency-**

To work, certain packages require additional packages. You may install all the dependencies you require using programs like Yum, Aptitude, and apt-get. You will have to install dependencies yourself if you're building from source or using dpkg or rpm.

### ***What is a package?***

A "**package**" is a bundled set of files and metadata that makes up a program, library, or piece of code. A package manager is typically used to distribute and install these packages after they have been compressed or archived.

**A package usually consists of the following:**

**Files**: The actual components of the software, including executable binaries, configuration files, libraries, documentation, and sometimes assets like images or templates.

**Metadata**: information about the package, such as its name, version number, dependencies, description, and sometimes cryptographic signatures for security.

### ***What are the types of packages?***

---

| **<mark>Package Manager Type</mark>** | **<mark>Linux Distributor</mark>** | **<mark>Information</mark>** | <mark>Commands</mark> |
| --- | --- | --- | --- |
| APT | Debian, Ubuntu | APT (Advanced Package Tool) is used for Debian-based systems. It handles deb packages. | 1) Install Package: apt install jenkins 2) Remove Package: apt-remove docker 3) To remove dependencies : apt autoremove 4) Update the repository: apt update 5) to search : apt-cache search apache |
| dpkg | Debian, Ubuntu | This is the low-level package manager on Debian-based systems. It directly handles the installation and removal of DEBU packages. | 1) to install: sudo dpkg-i \[package\] 2) To remove: sudo dpkg -r \[package\] 3) Remove the package along with the configuration file dpkg -p \[package\] |
| YUM (Yellowdog Updater, Modified) | Red Hat Enterprise Linux (RHEL), CentOS | YUM is used in RPM-based distributions for managing packages. It has been replaced by DNF in some distributions. | 1) Install package: sudo install nginx -y 2) To remove package: sudo yum remove nginx 3) To upgrade or update package: yum upgrade/update package 4) all the options: sudo yum -option 5) to see past work done related to packages: yum history |
| DNF (Dandified YUM) | Fedora, RHEL | DNF is the next-generation package manager used in Fedora and Red Hat Enterprise Linux (RHEL) 8 and later versions. | 1) It shows the list of packages: sudo dnf list available 2) Number of packages available (dnf list available) |
| RPM | Red Hat, CentOS, and Fedora | RPM (RPM Package Manager) is the package format and the package manager for many RPM-based distributions. | 1)to install package :rpm -i package-file 2) to remove package : rpm -r package-file 3) to query all the installed packages : rpm -qa or rpm -qa |
| Zypper | openSUSE | Zypper is used in openSUSE for package management. It handles RPM packages. | 1)To install package: sudo zypper install package-name 2)to update/upgrade package : sudo zypper update 3)To remove packages : sudo zypper remove package-name 4) to find Information about specific package: sudo zypper info package-name |
| Pacman | Arch Linux, Manjaro | Pacman is the package manager used in Arch Linux and its derivatives, like Manjaro. It manages the pkg.tar.xz packages. | 1)to install specific packages : pacman -S package\_name1 package\_name2 ... 2) To Remove packages : pacman -R package\_name 3)To remove a package and its dependencies: pacman -Rs package\_name 4) Upgrading packages: pacman -Syu |
| Snap | Ubuntu and other distributions supporting snaps | Snap is a universal package manager used across different distributions like Ubuntu, Fedora, CentOS, and more. It works with snap packages and offers sandboxed applications. | 1) Search application: snap find app\_name 2) Information about applications: snap info app\_name 3) List all Installed Applications : snap list 4) Updating Applications : sudo snap refresh app\_name 5)Removing application:sudo snap remove app\_name 6)Enable Applications :sudo snap enable app\_name 7) Disabling applications: sudo snap disable app\_name 8) Revert updated applications:sudo snap revert app\_name |
| Flatpak | Various distributions | Flatpak is another universal package manager that works across different Linux distributions to deploy and manage sandboxed applications. | 1) Below to enter the root user mode: Sudo -s 2) To install the application: flatpak install --from \[url of application\] |
| APK | Alpine Linux | APK is the package manager used in Alpine Linux, handling.apk packages. | 1)to install a package : apk add package-name 2)to remove or delete: apk delete package-name 3)to upgrade: apk add -u package-name 4)list installed packages:apk info package-name |

---

### **SYSTEMCTL :**

You must be familiar with the **systemctl** command if you work with Linux systems.

To manage the services, the systemctl command communicates with the SystemD service manager. Unlike the service command, it does not run the init script; instead, it interacts with the SystemD process to handle the services.

***Commands and Information:***

| <mark>Commands</mark> | <mark>Information</mark> |
| --- | --- |
| 1) Start/Stop service | sudo systemctl start/stop \[service-name\] |
| 2) Check the status | sudo systemctl status \[service-name\] |
| 3) To restart the service | sudo systemctl restart \[service-name\] |
| 4) Enabling a service causes the system to start the service upon reboot or whenever a computer starts up. | sudo systemctl enable \[service-name\] |
| 5) Enable and start the service at a time | sudo systemctl enable --now \[service-name\] |
| 6) To check if a service is enabled, | sudo systemctl is-enabled \[Service name\] |
| 7) Disabling a service | sudo systemctl disable \[service-name\] |
| 8) To prevent the service from starting | sudo systemctl mask \[service-name\] |
| 9) To check if service is enabled | sudo systemctl unmask \[service-name\] |
| 10) Computer control command a)power off b)reboot c)reboot while ignoring logged-in users | 1)systemctl poweroff 2) systemtctl reboot 3)systemctl -i reboot |
| 11) List the sockets in memory available for interprocess communication. a) types of sockets | 1)systemctl list-sockets 2)systemctl --show-types list-sockets |

---

***Conclusion -***

Package managers are key for Linux software; systemctl manages services under systemd. Understanding both ensures efficient system management.

---

**Kindly feel free to ask any queries in the section below. I'd be pleased to respond to them.**

**Please follow and use the heart❤❤ button below to express your support if you think this content is helpful 😊.**

**I appreciate you taking the time to read.**

thank you! @[Shubham Londhe](@TrainWithShubham)#Day07#90DaysofDevopschallenge #devops #PackageManager #ServiceManager #Cloud