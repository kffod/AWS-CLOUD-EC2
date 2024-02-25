# Cloud Computing Mini-Project: CV Builder Website Deployment on AWS EC2 Instance

## Project Overview
This mini-project is designed for the Cloud Computing subject, focusing on deploying a simple CV Builder website on an AWS EC2 instance. The goal is to gain hands-on experience with cloud infrastructure and deployment processes.

### Project Features
1. **CV Builder Website**: Create a basic CV Builder website where users can input their details and generate a formatted CV.
2. **AWS EC2 Instance**: Deploy the CV Builder on an AWS EC2 instance, utilizing the scalability and flexibility of cloud computing.
3. **Hands-on Learning**: Gain practical knowledge of setting up a web application in a cloud environment.

## Adventure Plan

### 1. Set Up Your AWS Cloud Environment
- **Log in to the AWS Console.**
- **Navigate to the EC2 service.**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/b0e723dbe26aee23a4a2c205f7b593abda5e4532/Step1-creating%20instance/step0.png)
- **Create a new EC2 instance for hosting your CV Builder website.**
- **Under `EC2 > instances > Launch` an instance**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/b0e723dbe26aee23a4a2c205f7b593abda5e4532/Step1-creating%20instance/step1.png)
- **Select OS as Amazon linux.**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/b0e723dbe26aee23a4a2c205f7b593abda5e4532/Step1-creating%20instance/step2.png)
- **Create Key pair for assesing VM.**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/b0e723dbe26aee23a4a2c205f7b593abda5e4532/Step1-creating%20instance/step3.png)
- **Select `.ppk` extension for puTTY and `.pem` for openSSH as you like.**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/b0e723dbe26aee23a4a2c205f7b593abda5e4532/Step1-creating%20instance/step4.png)
- **Configure the storage.**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/b0e723dbe26aee23a4a2c205f7b593abda5e4532/Step1-creating%20instance/step5.png)
- **Boom Launch the instance.**


![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/b0e723dbe26aee23a4a2c205f7b593abda5e4532/Step1-creating%20instance/step6.png)



- **You will see these screen after your instance is succesfully launched!**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/b0e723dbe26aee23a4a2c205f7b593abda5e4532/Step1-creating%20instance/step7.png)


### 2. Connecting and Configuring EC2 instance
- **Go to running instances Dashboard.**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step0.png)

- **I am connecting directly using console if you want to connect your instance you can connect it using puTTY or openSSH!**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step1.png)
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step2.png)

- **Granting admin previlage using sudo command.**
**Run the sudo su Command.**

  **Use the following command to switch to the root user and gain admin privileges:**

   ```bash
   sudo su
   ```
  ![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step3.png)

- **Update your Virtual Machine using following command:**
  ```bash
  yum update
  ```
  ![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step4.png)
- **After updating your system download git using following command:**
  ```bash
  yum install git -y
  ```
 ![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step5.png) 

- **After that clone these repository using following command:**
  ```bash
  git clone https://github.com/kffod/AWS-CLOUD-EC2.git
  ```
  **After that copy index.html,script.js,style.css from |CV Builder Code| folder and paste it into |/var/www/html| folder as shown below:**
  ```bash
  cd /AWS-CLOUD-EC2/CV Builder Code/
  mv * /var/www/html/
  ```
- **After that install httpd using following command:**
```bash
yum install httpd -y
```
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step6.png)

- **After installing httpd start httpd service using following command:**
```bash
systemctl start httpd
```
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step7.png)

**You can check whethier httpd service running or not using following command:**
```bash 
systemctl status httpd
```
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step8.png)


### 3. Accesing Your Website 
- **For accessing your cloud hosted website go to EC2 instance Dashboard and select your instance.**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/1f73774d51372f19698bc5ec34160374cf0e473c/Step2-Connecting%26Configering%20%20instance/step0.png)

- **After Selecting your instance go to your public IP address of EC2 instance**
  **In my case my public IP is `13.53.200.33`***
  **Open it in any browser , BOOM your website is deployed in cloud! :).**
![setup](https://github.com/kffod/AWS-CLOUD-EC2/blob/50f26ebda57bd7975ba05e2166af0454a986de6c/step3-final%20endpoint/endpoint.png)  


**NOTE: Stop the instance after you deploy successfully; otherwise, after the free trial limit is exceeded, you will be charged!**

Remember to enjoy the learning process and troubleshoot any challenges you encounter. Happy cloud adventures! 🚀✨!
