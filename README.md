The step-by-step process for Provisioning a Linux Server with a simple HTML page

The Public IP address of my landing page is 54.227.76.174

![Screenshot of HTML page in browser](https://github.com/user-attachments/assets/d1740e69-7c08-4f13-9b24-2de2bc2ddc3a)


STEP 1: PROVISION AN AWS EC2 INSTANCE
I logged in to AWS Management Console:
Went to AWS Console.
Launched an EC2 Instance:
Navigated to the EC2 Dashboard under "Compute."
Clicked on Launch Instance.
Configured the EC2 Instance:
![AWS_EC2_launch instance](https://github.com/user-attachments/assets/462d2e80-9458-4e9e-a769-54cd458b99f0)

Name: I entered a name for my instance (Exam_Project).
AMI: Selected an Amazon Machine Image (AMI). Clicked on Ubuntu Server 22.04 LTS.
![AWS_EC2_AMI_instance type](https://github.com/user-attachments/assets/ab43a77f-52f8-4414-ae71-e7b8f47d484c)

Instance Type: Choose an instance type (t2.micro, eligible for free tier).
Key Pair: I created a new key pair (examproject). Saved the private key file (.pem) to my computer.
![AWS_EC2_key pair setting](https://github.com/user-attachments/assets/c193bd4c-988f-4577-8207-d24b469ead1c)

Network Settings:
Ensured I allowed SSH traffic by selecting "Allow SSH from My IP."
Added a rule to allow HTTP traffic (port 80) from anywhere.
![AWS_EC2_networking setting](https://github.com/user-attachments/assets/2317b936-8f6c-4f57-8a83-6ebaa5018ed9)

Storage: I left the default storage or adjusted it as needed.
![AWS_EC2_storage setting](https://github.com/user-attachments/assets/e33e1e57-ce2d-42d3-9ad0-d20f70938460)

Clicked Launch Instance.
![AWS_EC2_launched instance successfully](https://github.com/user-attachments/assets/97e17202-5a00-4e79-a548-2f0779e92d3d)


Got the Public IP Address:
Once the instance is running, I go to the EC2 dashboard and copy the Public IPv4 address (54.227.76.174).
![AWS_EC2 INSTANCE_dashboard](https://github.com/user-attachments/assets/7cfac95f-f931-4768-8903-bdb1bd4b3374)

