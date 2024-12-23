THE STEP-BY-STEP PROCESS FOR PROVISIONING A LINUX SERVER WITH A SIMPLE HTML PAGE

The Public IP address for my landing page is 54.227.76.174

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


STEP 2: CONFIGURE TERMIUS FOR SSH CONNECTION

Installed Termius:
Downloaded and installed Termius from the Termius Website.

Added a New Host:
Opened Termius and clicked on New Host.
Host: Entered the EC2 instance's public IP address.
![Termius_Added new host](https://github.com/user-attachments/assets/518b06b7-f397-44c1-b3dd-bb90f0c3d44c)

User: Used ubuntu (default username for Ubuntu).
![Termius_Username](https://github.com/user-attachments/assets/32a2f539-685c-4216-82d4-0dab20d0f3ef)

Authentication:
Selected Private Key and uploaded the .pem key file downloaded during key pair creation.
![Termius_key pair](https://github.com/user-attachments/assets/0c43b120-2a24-4344-89cf-91961c3a9eb8)

Saved the host configuration.

Connected to the EC2 Instance:

Clicked on the saved host to connect.

![Termius_authentication](https://github.com/user-attachments/assets/baf607ae-ce5d-474c-8c87-7151c912e4ca)

Termius terminal is launched

![Termius_terminal](https://github.com/user-attachments/assets/155f6029-c227-4d7d-8143-60e0b40cdb1e)


STEP 3: INSTALLED APACHE2 WEB SERVER

Updated the System: Ran the following commands to update the package lists:

sudo apt update -y

Installed Apache2: Installed the Apache2 web server using:

sudo apt install apache2 -y

Started and Enabled Apache2: Ensured Apache2 starts and is enabled to run on boot:

sudo systemctl start apache2

sudo systemctl enable apache2

Tested Apache2 Installation:

Opened a browser and visited the public IP address: 54.227.76.174.

The default Apache2 page will be displayed.
![APACHE2 WORKING](https://github.com/user-attachments/assets/dc1be4fc-6778-4c35-8648-6fa502fad5ac)


STEP 4: DEPLOYING MY SIMPLE HTML LANDING PAGE

Navigated to the Apache2 Web Root:

Created a folder: mkdir altschool_project_exam

Cd to the file: cd altschool_project_exam

Copied and installed the GitHub project link: wget https://github.com/inyenepaul/AltSchool-Exam-Project.git

Copied the GitHub zip link: wget https://github.com/inyenepaul/AltSchool-Exam-Project/archive/refs/heads/main.zip

Installed unzip: apt install unzip

Unzipped the zip file: unzip main.zip

cd to the folder: AltSchool-Exam-Project-main

Moved the folder to the server: mv * /var/www/html/

Cd to the path: cd /var/www/html/

Checked the status of apache2: systemctl status apache2

Enabled apache2: systemctl enable apache2

Started apache2: systemctl start apache2

Reloaded the public IP address (54.227.76.174) in the browser: The landing page is displayed
