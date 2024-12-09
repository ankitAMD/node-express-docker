Project Video Link and Github Repo ---

Youtube - https://www.youtube.com/watch?v=YOqUAfNtXFE

Github Repo - https://github.com/piyushgarg-dev/node-express-docker

Architechture - https://app.eraser.io/workspace/D9gMWx8fRkfXbxo51D32


Timestamp - 12/04/2023
Video Timestamps and Topics

00:03 - Introduction to the staff room session

02:22 - Discussion on containerization and deployment

06:36 - Setting up TypeScript configuration and basic Express application

08:28 - Building and running the project with npm

12:19 - How to copy package.json and package-lock.json in DevOps

14:59 - Copying and organizing source code within containers and understanding Dockerfile usage

19:00 - Package management and building distribution in DevOps

20:53 - Running NPM and Docker commands

24:58 - Containerized Node.js application with Docker image

27:11 - Hosting code on a cloud and using image registries

31:12 - Creating and configuring AWS IAM user and access keys

33:05 - Setting up ADB and Docker build commands

36:54 - Introduction to Elastic Container Service (ECS)

38:51 - Setting up own clusters for staging and production

43:00 - Using ECR for image management

44:59 - Monitoring container health with health route

48:44 - Deployment options and rolling updates

50:41 - Handling bugs and scaling in DevOps

54:44 - Autoscaling for ECS service

56:34 - Autoscaling based on traffic and memory utilization

1:00:29 - Setting up and monitoring task health status and target group

1:02:11 - Setting up load balancer and target group for container management

1:06:07 - Discussing Kubernetes deployment and scaling in DevOps

1:07:53 - Managing zero running tasks in DevOps

Project - type script Project
Application Type - Express application
Scrpts -  1. Start script 
         
          2. Build script - Convert TypeScript project to JavaScript
          
          Package.json -

          3. Dependencies - Express - 4.18.2
             
             DevDependencies - Express - 4.17.21 
                               
                               TypeScript - 5.3.3  

          4.tsconfig.json - Typecript configuration file
            
            1. SourceRoot - src
            
            2. OutDir - dist (After compilation)
          
          5. Installed Modules -
             npm ci 
             (created node_modules folder) 

          6. After running build script
             npm run build

             compiled files are in dist folder (index.js)

          7. To start the application
             npm start

         Output - 
         http://localhost:8000/
         
         ![image](https://github.com/user-attachments/assets/bb163d19-ff93-4d01-998e-b5bfd1989b42)

         https://github.com/user-attachments/assets/bb163d19-ff93-4d01-998e-b5bfd1989b42

         http://localhost:8000/health

         ![image](https://github.com/user-attachments/assets/7578d896-68f9-41f7-b1d9-4d5f122cb091)

         https://github.com/user-attachments/assets/7578d896-68f9-41f7-b1d9-4d5f122cb091



https://github.com/user-attachments/assets/0990252b-d852-44ab-ba62-85e7b07b91d0
             
