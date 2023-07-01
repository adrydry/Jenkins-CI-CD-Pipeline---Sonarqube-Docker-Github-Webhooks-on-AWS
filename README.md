# Jenkins-CI-CD-Pipeline-Sonarqube-Docker-Github-Webhooks-on-AWS




**1 : Download a static template website and save it**

**2 : Create 3 EC2 instances**

- Create our Security Group and make sure to open the port 22, 80, 8080, 9000

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/4ceee428-8d7a-4d1c-9571-032197fd4294)

We will create 3 EC2 instances: Jenkins, Sonarqube and Docker

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/a22effac-0f84-4aa5-a518-8c2c6ba83463)

**3: Connect to the instances using the public IP and Mobaxterm**

 ![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/bdeced0b-c6e4-48f4-8d39-26f7b415a1b7)

**4: Update the Jenkins server and install Jenkins**

- Install Java first
  
  ![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/ef8cedc6-a07f-4887-9a31-5dea46d315fe)

- Install Jenkins
  
Go on the browser and paste the Public IP adress of our server and make sure to open it with the port 8080. The jenkins page is available.

To verify also if the jenkins server is installed, we can use systemctl status jenkins
Paste the access token and configure the jenkins server

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/f1bd5025-6e5a-43e9-8419-297afb8dba5a)

**5: Set up the Jenkins server and Create a freestyle job**

- Click on install plugins. These plugins will help us to integrate easily Jenkins with other tools 
![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/b06d14be-354d-4e5a-a459-a56f9a744153)

- Click on create a Job and choose Freestyle job and name it **Automated-Pipelines**. Paste the repository where the source code is located **https://github.com/Areez01/Jenkins-Sonarqube-Docker.git**.

- Make sure to enabe **Github hook trigger for Gitscm polling** to ensure that whenever the developpers make a new change on the git repository, jenkins will trigger it automatically

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/1e0a1a40-ce79-4b71-a02e-7862f0748001)

**6: Create a Webhook**

With webhook, whenever the developper make a change on the code or repository, it will trigger the jenkins automatically and jenkins will pull the code from the github. To configure a webhook:

- On the git repository, Go to settings, click on add a webhook and paste the URL of our job in the Jenkins server. Save

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/b8ff49db-7a83-4b93-9782-698d51fa7db5)

Make sure to enable pushes and pull requests

![2](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/524f89e3-c513-4183-bac7-1601b1241b0d)

Our webhook is created
![3](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/958185d5-2de0-4b73-a36b-84a6f31cf6e9)

**7: Build our project**

Our first build is successfull
![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/1de3fc80-5fd1-4c61-9c9b-b7963dcb60a8)

**8: Connect to our Sonarqube server and install Sonarqube**

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/478a5163-1816-440e-91fd-ae39b357804d)

- install Java

- Go to sonarqube.com and download the community Edition with wget link

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/6208f809-2826-4fdc-8fa7-f47a14a7856d)

We need to unzip this file:

- Install unzip with: sudo apt install unzip 

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/b6250b88-79ca-46cb-b376-121963358253)

- unzip our Sonarqube file

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/1442391b-a9c7-47bc-bef4-9c560d732abd)

- Access the unzip directory and go to the bin directory. .sonar.sh file is available

   ![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/d7557e4c-3216-47ef-a3ba-4320eec5e277)

- Run ./sonar.sh file

  ![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/dfba5fbe-1cbc-4163-ad1a-3f50e72fd4ba)

 **9-Sonarqube is operationnel. Let's verify that by using the ip adress of the sonarqube server on the browser**

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/68726f17-f586-4728-b512-22ee5d8a1d1c)

The default username and password of Sonarqube is **Admin**. We will modify these information at our first login. Access our Sonarqube platform

- Choose to add our project manually. Create a project and click on Set up

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/3c845a10-bd80-4fac-87bb-ef5e405594f2)

Choose our CI tool: Jenkins

Select our Devops tool: Github

Configure analysis
Create a jenkinsfile: other
Copy our projectkey
Click on finish 
Go to the home account, go to security and create token. Copy the token

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/a2c39219-b73e-413d-9e40-bb8c269d9696)

Go to jenkins, Manage plugins and install the plugins Sonarqube scanner and ssh2 easy

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/dba506b4-e85c-49dc-8091-670869dd3042)


![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/584b10d0-5919-4729-8d41-0832636bc722)


Go to Manage tools on jenkins and add Sonarqube scanner

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/d12c4784-bf3f-4dbe-83df-9f59878c398c)

Go to configuration on jenkins and we will see Sonarqube servers

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/13463e8d-1ef8-4950-a615-439b9c76cfcc)

Go to the pipeline on configure to add a step to execute the sonarqube scanner on build step

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/609ff391-6905-4080-ad36-5f82432d06f1)

Go to congigure system and add jenkins as a server authentification token

Build our pipeline

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/c9ee7955-5498-4c2c-8895-004a51620cd9)
![14](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/44fb51e4-1dba-43db-9fc5-542d6610660b)


Now that our code passed the security analysis, we can deploy it on our Docker server

- Install Docker on our Docker server

- Go to jenkins server. Switch as a user jenkins and try to ssh to the docker server. It will not work.
To troubleshoot that, go on Docker server, as a root , open the configuration file and enable password authentification by remove the # and by changin yes to no


- Go to the pipeline and look at server group center

- Add the server list and paste the ip of the docker server













