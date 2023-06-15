# Jenkins-CI-CD-Pipeline-Sonarqube-Docker-Github-Webhooks-on-AWS




**1 : Download a static template website and save it **

**2 : Create 3 EC2 instances**

- Create our Security Group and make sure to open the port 22, 80, 8080, 9000

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/4ceee428-8d7a-4d1c-9571-032197fd4294)

We will create 3 EC2 instances: Jenkins, Sonarqube and Docker

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/a22effac-0f84-4aa5-a518-8c2c6ba83463)

**3: Connect to the instances using the public IP and Mobaxterm**

**4: Update the Jenkins server and install Jenkins

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/f1bd5025-6e5a-43e9-8419-297afb8dba5a)

**5: Set up the Jenkins server and Create a freestyle job**

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/b06d14be-354d-4e5a-a459-a56f9a744153)

**6: Create a Webhook**

With webhook, whenever the developper make a change on the code or repository, it will trigger the jenkins automatically and jenkins will pull the code from the github

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/b8ff49db-7a83-4b93-9782-698d51fa7db5)

![2](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/524f89e3-c513-4183-bac7-1601b1241b0d)

![3](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/958185d5-2de0-4b73-a36b-84a6f31cf6e9)

**7: Build our project**

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/1de3fc80-5fd1-4c61-9c9b-b7963dcb60a8)

**8: Connect to our Sonarqube server and install Sonarqube**

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/478a5163-1816-440e-91fd-ae39b357804d)

- update the repository and install Java 17 which is compatible with Sonarqube

- Go to sonarqube.com and download the community Edition with wget link

![1](https://github.com/adrydry/Jenkins-CI-CD-Pipeline---Sonarqube-Docker-Github-Webhooks-on-AWS/assets/102819001/18938f91-a5d7-4f51-a05c-252cc4bc8a42)

















