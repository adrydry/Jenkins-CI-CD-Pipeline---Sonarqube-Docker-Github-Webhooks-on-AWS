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

- update the repository and install Java 17 which is compatible with Sonarqube

- Go to sonarqube.com and download the community Edition with wget link

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/18938f91-a5d7-4f51-a05c-252cc4bc8a42)

















