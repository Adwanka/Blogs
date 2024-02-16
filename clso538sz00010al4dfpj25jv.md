---
title: "🚀Basic Git and GitHub for DevOps Engineers"
datePublished: Fri Feb 16 2024 04:18:09 GMT+0000 (Coordinated Universal Time)
cuid: clso538sz00010al4dfpj25jv
slug: basic-git-and-github-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703837965716/64cc6af9-01a1-4f0f-a6d5-c7350f6c90f3.jpeg
tags: github, version-control, git, devops, devops-journey, shubhamlondhe, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity, day-08

---

---

### Introduction -

These days, we do everything online using software, services, or websites. To ensure that everything is done correctly and without error or failure, we have adopted all of the DevOps practices. One of the practices that is most important to us is source control.

It is complicated if someone accidentally deletes a file, and we do not have access to restore it. It is also vital to document what, who, where, and how the code is changed. and that is known as version control since it is constantly updated.

In order to simplify file systems, we are learning the fundamentals of Git and GitHub version control technologies today, on Day 8.

---

### What is Git?

GIT stands for Global Information Tracker.

Git is a distributed version control system that tracks changes in any set of computer files, usually used for coordinating work among programmers who are collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows.

Git was first developed in 2005 by Linus Torvalds for use in the development of the Linux kernel, with assistance from other kernel engineers. Junio Hamano has been the main maintainer since 2005. Every Git directory on every computer is a fully functional repository with full version tracking capabilities and a complete history, just like most other distributed version control systems, and it is not dependent on a central server or network connectivity. This is in contrast to most client-server solutions. Git is open-source software distributed under the GPL-2.0 exclusively. It is free to use.

---

### What is Github?

GitHub is a code-hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

It is a Microsoft subsidiary that provides all of Git's distributed version control and source code management (SCM) features, in addition to a few extras.

---

## What is version control?

A crucial software development technique for monitoring and controlling changes made to code and other files is version control, commonly referred to as source control or revision control. It has a tight connection to source code management.

Use version control to save your work and coordinate code changes across your team.

The version control system saves a snapshot of your files so that you can review and even roll back to any version of your code.

### How many types of version controls do we have?

There are two main types of version control systems: centralized version control systems and distributed version control systems.

1. **Centralized Version Control:**
    

Centralized source control systems are based on the idea that "there's a single "central copy of your project somewhere. Programmers will check in (or commit) their changes to this central copy.

Other Programmers can then see this changes

Programmers no longer keep many copies of the files on their hard drives manually.

Some of the central source control system used are Team Foundation version control (TFVC), Subversion, and Perforce

1. **Distributed Version Control:**
    

Over time, a distributed version control system becomes more important. popular are GIT and Mercurial.

These systems don't necessarily rely on a central server to store all the versions of the project files. Instead, every developer "clones" a repository copy and has the project's completed history on their local storage.

Getting new changes from a repository is called "pulling," and moving new changes to a repository is called "pushing."

### Why do we use distributed version control over centralized version control?

* In distributed version control, every developer's computer mirrors the whole codebase, whereas in centralized version control, the server's central repository delivers the most recent code to the client server.
    
* Whereas distributed control has local repositories, centralized control does not have any.
    
* Comparatively speaking, distributed version control operates more quickly than a centralized system.
    
* When a central server fails in centralized systems, all versions are terminated; however, in distributed systems, development is unaffected by main server failures.
    

---

1. Create a new repository on GitHub and clone it to your local machine
    
    Choose, then click <mark>New repository</mark> in the upper-right corner.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706355396289/b5de310a-5be4-40cc-91d4-7c05dd271d72.png align="left")
    
    Use the <mark>Owner</mark> drop-down menu to select the account you want to own the repository, and type a name for your repository and an optional description.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706356156688/f2f978bb-ce34-4e74-9119-25061f787395.png align="center")
    
    You can create a <mark>README</mark>, which is a document describing your project.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706356301180/3ba24e02-6c4b-43f3-a272-8735dc87480a.png align="center")
    
    Click <mark>Create repository</mark>.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706356508681/d97493bf-33ff-46f3-a10c-ba043b7a6894.png align="center")
    
    Now we need to clone the repository.
    
    The <mark>git clone</mark> command is used to create a copy of a specific repository or branch within a repository.
    
    Git-cloning can be done in a variety of ways.
    
    1. Git clone (URL)
        
    2. Git clone --mirror
        
    3. Git clone --single-branch
        
    4. Git clone --sparse
        
2. Make some changes to a file in the repository and commit them to the repository using Git and Push the changes back to the repository on GitHub
    
    | Action | Git command |
    | --- | --- |
    | Add all the new files. | git add . |
    | Commit changes. | git commit -m '&lt;commit\_message&gt;' |
    | Get an idea of the git command to use next. | git status |
    | a push to GitHub | git remote add origin |
    
    ![Git - Recording Changes to the Repository](https://git-scm.com/book/en/v2/images/lifecycle.png align="left")
    
    **Kindly feel free to ask any queries in the section below. I'd be pleased to respond to them.**
    
    **Please follow and use the heart❤❤ button below to express your support if you think this content is helpful 😊.**
    
    **I appreciate you taking the time to read.**