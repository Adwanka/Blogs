---
title: "🚀Deploying a Two-Tier Flask App with MySQL Using Docker on Linux"
datePublished: Wed Jan 10 2024 18:50:43 GMT+0000 (Coordinated Universal Time)
cuid: clr84yv8q000009kz6dmk5df5
slug: deploying-a-two-tier-flask-app-with-mysql-using-docker-on-linux
tags: linux, docker, aws, python, mysql, dbms, dockerfile, docker-network, shubhamlondhe, trainwithshubham, dockercompose, dockervolume, two-tire-application, dockeimages, dcokercontainer

---

---

### **Introduction:**

The smooth and scalable operations of modern application deployment are dependent on containerization. This blog explains how to use Docker on a Linux operating system to deploy a two-tier Flask application that communicates with a MySQL database. User-submitted messages are displayed on the frontend of the application and are stored in the database.

---

### **Prerequisites:**

* Basic understanding of Docker concepts
    
* Python and Flask installed on the local system
    
* Docker installed on a Linux operating system
    

MySQL server installed locally or accessible externally

---

***{{{First Step*: Configuring the Application for Flask}}}**

Clone the repository on GitHub.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704901414834/e75fd7b7-7b34-4454-bd1c-750f50994ccd.png align="center")

---

***{{{Second step*: create a Dockerfile}}}**

To start the Flask application, create a Dockerfile with the environment, dependencies, and commands specified.

```dockerfile


# Use an official Python runtime as the base image

FROM python:3.9-slim

# Set the working directory in the container

WORKDIR /app

# install required packages for system

RUN apt-get update \ && apt-get upgrade -y \

&& apt-get install -y gcc default-libmysqlclient-dev pkg-config \

&& rm -rf /var/lib/apt/lists/*

# Copy the requirements file into the container

COPY requirements.txt.

# Install app dependencies

RUN pip install mysqlclient

RUN pip install --no-cache-dir -r requirements

RUN pip install --no-cache-dir -r requirements.txt

# Specify the command to run your application

CMD ["python", "app.py"]
```

---

***{{{Third Step*: Setting Up the Docker Network}}}**

Set up a Docker network so that containers can communicate with each other. Construct a bridge network to link the Flask application's front-end and back-end tiers.

> **List all networks:**
> 
> *<mark>docker network ls</mark>*
> 
> **Inspect a network:**
> 
> *<mark>docker network inspect &lt;network_name&gt;</mark>*
> 
> **Create a new network:**
> 
> *<mark>docker network create --driver &lt;driver_type&gt; &lt;network_name&gt;</mark>*
> 
> **Connect containers to a network:**
> 
> *<mark>docker network connect &lt;network_name&gt; &lt;container_name&gt;</mark>*
> 
> **Disconnect containers from a network:**
> 
> *<mark>docker network disconnect &lt;network_name&gt; &lt;container_name&gt;</mark>*
> 
> **Remove a network:**
> 
> *<mark>docker network rm &lt;network_name&gt;</mark>*

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704902399679/a965efec-4f44-47ac-905f-b0bdac9e4e60.png align="center")

---

**{{{Fourth Step: Docker Volume Creation}}}**

Set up a Docker volume to persist MySQL data, ensuring data persistence across container restarts.

> **Make directory:** ***<mark>mkdir volume</mark>***
> 
> **Change the directory :** ***<mark>cd flask-app</mark>***
> 
> **Change the directory to Volume : *<mark>cd volume</mark>***
> 
> **Create Volume : *<mark>docker volume create --name [volume name] --opt type=none --opt device=home/ubuntu/flask-app/volume --opt o=bind</mark>***
> 
> ***#Now attach volume***
> 
> ***<mark>docker run -d -p &lt;host_port&gt;:&lt;container_port&gt; --mount source=[volume name], target=/data imagename:tag</mark>***
> 
> **List all networks: *<mark>docker network ls</mark>***
> 
> **Inspect a network:** ***<mark>docker network inspect &lt;network_name&gt;</mark>***
> 
> **Create a new network:** ***<mark>docker network create --driver &lt;driver_type&gt; &lt;network_name&gt;</mark>***
> 
> **Connect containers to a network:** ***<mark>docker network connect &lt;network_name&gt; &lt;container_name&gt;</mark>***
> 
> **Disconnect containers from a network:** **<mark>docker network disconnect &lt;network_name&gt; &lt;container_name&gt;</mark>**
> 
> **Remove a network:** ***<mark>docker network rm &lt;network_name&gt;</mark>***

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704903862752/684abc0a-0d23-454c-9c74-dc8b18315d94.png align="center")

**{{{Fifth Step: Configuring the MySQL Database}}}**

Set up a MySQL database and create a table to store messages submitted by users

> <mark>docker exec -it [container ID] bash</mark>
> 
> <mark>bash-4.4# mysql -u root -p</mark>
> 
> <mark>enter password</mark>
> 
> <mark>mysql&gt;use testdb;</mark>
> 
> <mark>show tables;</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704904452587/0b63c9ab-68d1-46af-9ca6-db174b02ec1e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704904511729/698987bb-6c74-489d-b626-cecc1e06622d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704904572581/751f2d32-39c9-4094-bec2-7cfb6bc2527e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704904643502/e1cc625b-4bf6-46a0-8fb7-55bcf9d890ef.png align="center")

**{{{Sixth Step: Building and Deploying the Docker Containers}}}**

Access the deployed Flask app via the browser, submit messages, and confirm that they are stored in the MySQL database and shown on the frontend.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704904967280/fb13eb70-b837-456a-9169-8f841079ca63.png align="center")

---

## **Conclusion:**

Following these procedures resulted in the successful deployment of a two-tier flask program that interacts with a MySQL database on a Linux operating system. This containerized system ensures portability, scalability, and easy management for modern application deployments.

---

**Kindly feel free to ask any queries in the section below. I'd be pleased to respond to them.**

**Please follow and use the heart❤❤ button below to express your support if you think this content is helpful 😊.**

**I appreciate you taking the time to read.**

@[Shubham Londhe](@TrainWithShubham)