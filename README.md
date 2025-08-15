Navigation Menu
sign in 
dosapatnisravani 
/
devops-task-8
Public
Code
Issues
Pull requests
devops-task-8
/README.md
dosapatnisravani
dosapatnisravani
2 hours ago
97 lines (73 loc) · 3.1 KB

Preview

Code

Blame
Simple Java CI/CD with Jenkins and Maven
This project, hello-java-maven, is a simple demonstration of a Continuous Integration (CI) pipeline using Jenkins to automatically build a Java application with Maven. It serves as a basic, hands-on introduction to CI/CD principles.

📋 Table of Contents
Objective
🛠️ Technologies Used
📂 Project Structure
🚀 How to Run This Project
Prerequisites
Step-by-Step Guide
✅ Expected Outcome
🎯 Objective
The goal of this project is to learn the fundamentals of setting up a Jenkins Freestyle job to compile and package a simple "Hello World" Java application managed by Apache Maven.

🛠️ Technologies Used
Java (JDK 8 or 11)
Apache Maven
Jenkins
Docker (for running Jenkins)
Git
📂 Project Structure
The project consists of two essential files:

.
├── src/
│   └── main/
│       └── java/
│           └── HelloWorld.java   # The Java source code
└── pom.xml                       # The Maven build configuration
🚀 How to Run This Project
Follow these instructions to replicate the CI pipeline on your local machine.

Prerequisites
Make sure you have the following software installed:

Git
Java JDK 8 or 11
Apache Maven
Docker Desktop
Step-by-Step Guide
Clone this Repository

git clone [https://github.com/](https://github.com/)[your-username]/[your-repo-name].git
cd [your-repo-name]
Start Jenkins via Docker Run the following command in your terminal to download and start the Jenkins container.

docker run -p 8080:8080 jenkins/jenkins:lts
Access Jenkins at http://localhost:8080.
Follow the on-screen instructions for the initial setup (you'll need the admin password from the Docker logs).
Configure Jenkins

In the Jenkins dashboard, navigate to Manage Jenkins → Global Tool Configuration.
Scroll down to Maven, click Add Maven, and give it a name (e.g., Maven 3.8.6). Ensure Install automatically is checked. Save the configuration.
Create the Jenkins Job

On the dashboard, click New Item.
Enter a name (e.g., hello-java-maven-build), select Freestyle project, and click OK.
Configure the Build Step

In the job configuration page, scroll down to the Build Steps section.
Click Add build step and select Invoke top-level Maven targets.
In the Goals field, enter:
clean package
Click Save.
Run the Build

After saving, you'll be on the job's main page. Click Build Now to start the pipeline.
✅ Expected Outcome
After the build completes, check the build history. Click on the build number and then go to Console Output. If everything was set up correctly, you should see the BUILD SUCCESS message at the end of the log.
