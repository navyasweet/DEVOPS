# DEVOPS PROJECT 


## Table of Content:

  * [Overview](#overview)
  * [Motivation](#motivation)
  * [Step By Step Process](#stepbystepproces)
  * [Potential Opportunities of project](#potential-opportunities)

## Overview :

  “DevOps is vital for modern software development due to its ability to accelerate delivery, enhance collaboration, improve quality, optimize resources, and prioritize a customer-centric approach. It reduces costs, mitigates risks, supports scalability, and fosters a culture of continuous learning and improvement, making it essential for agile and efficient development processes.”
   DevOps is like the ultimate tag-team duo of software development. It's all about bringing together the Dev and Ops teams, with a touch of automation, to create a lean, mean
   development machine. With DevOps, we can speed up the software development lifecycle, giving top-notch quality products and happy customers with swift and reliable software releases.

## Motivation:

  The craze for DevOps in the IT industry stems from its transformative advantages. DevOps accelerates software delivery through continuous integration, testing, and deployment. It
    enhances collaboration among development and operations teams, breaking down silos and promoting a shared responsibility model. This synergy leads to improved product quality, reliability, and faster feedback cycles.
  
  Emciency is bolstered by automation, optimizing resource utilization and reducing costs. Customer satisfaction is heightened through quicker feature releases and responsiveness to feedback. Risk mitigation occurs via smaller, manageable updates and robust monitoring, ensuring rapid issue detection and resolution. Scalability and ﬂexibility enable businesses to adapt swiftly to market changes
 
  Furthermore, DevOps cultivates a culture of continuous learning and improvement, fostering innovation and adaptability. The amalgamation of these beneﬁts propels organizations
    towards greater competitiveness, innovation, and customer-centricity, making DevOps a crucial paradigm in modern IT landscapes.



## Step By Step Process :

In the provided steps, the DevOps pipeline is integrated using Maven, SonarQube, and Jenkins:

1.	Setting Up Version Control with Git & Connecting Git and GitHub with
    Git Bash: Install Git:
  	 Follow the steps below to install Git on your system:
     Install Git by downloading the appropriate installer from the omcial Git website.
     Run the installer and follow the installation wizard.

    Conflgure Git: Open Git Bash.
    Conﬁgure your username and email for Git globally using the following commands:
  	
     ( `git conﬁg` commands are used to conﬁgure Git globally with a username and email, establishing version control)

  	     git conflg --global user.name "Your GitHub Username" git conflg --global user.email "Your GitHub Email"
  	
    Create a New Repository on GitHub:  Log in to your GitHub account.
      Click on the "+" icon in the top right corner and choose "New repository." Follow the instructions to create a new repository.
  	
    Connect Git and GitHub:
     Initialize a Git repository locally:
  	
         cd Desktop/my-app # Navigate to your project directory

         git init # Initialize a new Git repository

         git add . # Add all ﬁles to the staging area
         git commit -m "Initial commit"
 
   Add the GitHub repository as the remote origin:
   
         git remote add origin https://github.com/YourUsername/YourRepository.git

  ![image](https://github.com/navyasweet/DEVOPS/assets/134292286/c2f22bfa-d3a1-4fac-9783-bb40ff8199ad)
    
  Push your code to GitHub:
   
      git push -u origin main # Or use the appropriate branch name
    
  ![image](https://github.com/navyasweet/DEVOPS/assets/134292286/079ca362-8939-4cf9-a059-f1ac6f8f23de)
  
2.	Maven for Build Automation:
   
     Download the Maven binary zip ﬁle from the omcial Apache Maven website.
  	 Extract the zip ﬁle to a directory of your choice.
  	 Add the Maven `bin` directory to your system's PATH variable.
     `mvn package` and similar Maven commands are used to build and package the application.
     Maven is integrated to handle the build process, manage dependencies, and ensure the application is correctly packaged.
  	
  ![image](https://github.com/navyasweet/DEVOPS/assets/134292286/e5fe4b52-0f1e-4ee2-b071-2bac8d1a0571)

3.	Code Quality Analysis with SonarQube:

    Download the SonarQube distribution from the omcial SonarQube website.
  	Extract the downloaded zip ﬁle to a directory of your choice.
    Navigate to the SonarQube directory and run the appropriate start command for your system
  	(e.g., `bin/{operating_system}/sonar.sh` for Unix-like systems).
    Conﬁguration for SonarQube is provided to analyze the code quality.
    The `sonar:sonar` Maven goal is used to trigger SonarQube analysis, providing insights into code quality, bugs, vulnerabilities, and code smells.

   ![image](https://github.com/navyasweet/DEVOPS/assets/134292286/db591966-935a-42eb-a86b-2fe53e584e8d)

4.	Continuous Integration with Jenkins:

    Jenkins is set up to automate and orchestrate the entire process.
    Jenkins jobs are created to execute the Maven commands for building and analyzing the code.
    Jenkins is conﬁgured to trigger the builds and quality analysis automatically, providing continuous integration.

  ![image](https://github.com/navyasweet/DEVOPS/assets/134292286/f12b00bc-021d-46dc-b432-2083fe1ba671)

  
5.	Integration of CI/CD Pipeline:
   
    Creating a CI/CD Pipeline using Jenkins, Maven, and SonarQube:
  	
 ![image](https://github.com/navyasweet/DEVOPS/assets/134292286/5eb39072-ff6c-4baf-82a4-9e002e02b2b2)

 Install and Conflgure Jenkins :
    Jenkins is used to create pipelines that automate the entire build, test, and deployment process.
    Follow these steps outlined below to install and conﬁgure Jenkins.: Download the Jenkins WAR ﬁle from the omcial Jenkins website.
    Open a terminal and run `java -jar jenkins.war` to start Jenkins (you may specify a port with `--httpPort=8080`).
    Access Jenkins by opening a web browser and navigating to
          `http://localhost:8080`.

Create a New Jenkins Pipeline:

   Open Jenkins in your web browser (`http://localhost:8080` by default). Click on "New Item" to create a new pipeline.
   Choose "Pipeline" and give it a name (e.g., "My Pipeline"). Click "OK" to create the pipeline.

Conflgure Pipeline Settings:

  -	In the pipeline conﬁguration page, scroll down to the "Pipeline" section.
  -	Deﬁne your pipeline script (e.g., using a Jenkinsﬁle, or you can use the pipeline script directly in the conﬁguration)
  Integrate with
   Git: its url is connected and the java code id retrived using the conﬁgure settings in devops.
   Maven:it is central to these pipelines, managing dependencies and building the application.
   SonarQube:SonarQube analysis is triggered as part of the build process to maintain code quality.

Save and Build the Pipeline:

*Within your pipeline script, use stages to deﬁne your build, test, and SonarQube analysis steps.
*Utilize the Maven tool to build your project. For example:

```
stage('Build') {
steps {
     sh 'mvn clean install'
   }
   }
  ```

 * Integrate SonarQube analysis using the SonarQube Scanner for Maven. For example:
   ```
     stage('SonarQube Analysis') { steps {
     sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=my_app - Dsonar.projectName=my_app -Dsonar.host.url=http://localhost:9099 - Dsonar.login=your_sonar_token'
    }
    }
   ```
ﬁnally u can see pipelines bulid and are tested in jenkins as below image:

 ![image](https://github.com/navyasweet/DEVOPS/assets/134292286/9f6d6774-7696-4031-80c1-3229de9e3445)

Now, Jenkins will automatically execute the deﬁned pipeline, integrating Git, Maven, and SonarQube, and providing a streamlined CI/CD process for your project. Make sure to replace placeholders like `YourUsername`, `YourRepository`, `my_app`, and
`your_sonar_token` with appropriate values for your setup.

This integrated setup demonstrates a typical DevOps approach where version control, build automation, code quality analysis, and continuous integration are tightly connected. Maven serves as a fundamental tool for building and managing dependencies, while SonarQube enhances code quality. Jenkins acts as the orchestrator, automating the pipeline and enabling continuous integration and deployment. The goal is to achieve faster, more reliable software development with higher-quality code through automation and collaboration.


  

  
## Technologies Used :

![5](https://github.com/navyasweet/DEVOPS/assets/134292286/092941b5-5dd2-498d-8fe7-0efa17469b11)
![4](https://github.com/navyasweet/DEVOPS/assets/134292286/4d4fccde-9223-4f15-8562-130335c9d1ed)
![3](https://github.com/navyasweet/DEVOPS/assets/134292286/8e322db8-9acb-4726-b0a8-b4849a6b73a9)
![2](https://github.com/navyasweet/DEVOPS/assets/134292286/9dc2bee6-eda8-41f9-a6d6-4bf3694caa1e)
![1](https://github.com/navyasweet/DEVOPS/assets/134292286/e6562e62-67da-4fb1-8b99-f481b1ac2609)
![tool3](https://github.com/navyasweet/DEVOPS/assets/134292286/8b08b6f2-a976-4843-b3ba-4e37a5f9c961)
![tool2](https://github.com/navyasweet/DEVOPS/assets/134292286/49ea0e51-f690-42aa-bc00-c950e280f2ce)
![tool1](https://github.com/navyasweet/DEVOPS/assets/134292286/ce3ec9bb-bf97-4b59-bca6-9ee64ea71595)


 
## potential opportunities :

* Version Control Systems (VCS):
  -Git
* CI/CD Servers:
  -Jenkins
  -Travis CI
  -CircleCI
* Build Tools:
  -Apache Maven
  -Gradle
  -npm (Node Package Manager)
* Containerization:
  -Docker
  -Podman
* Container Orchestration:
  -Kubernetes
* Configuration Management:
  -Ansible
  -Chef
* Artifact Repository:
  -JFrog Artifactory
* Testing Frameworks:
  -JUnit
  -pytest
  -RSpec
* Static Code Analysis:
  -SonarQube
  -ESLint
* Continuous Testing:
  -Selenium
  -Jest
* Collaboration and Communication:
  -Slack
  -Microsoft Teams
* Cloud Platforms:
 -AWS CodePipeline
 -Azure DevOps Services
