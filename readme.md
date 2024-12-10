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

         https://github.com/ankitAMD/node-express-docker/blob/main/Output2.jpg

         http://localhost:8000/health

         ![image](https://github.com/user-attachments/assets/7578d896-68f9-41f7-b1d9-4d5f122cb091)

         https://github.com/ankitAMD/node-express-docker/blob/main/Output1.jpg


            8. Command to merge the code if there are any changes from remote github repo
               git fetch
               git status
               git merge origin/main

            9. Command to push the code to remote github repo
               git add .
               git commit -m "message"
               git push -u origin main

            10. Now we create dockerfile and in that we create multiple stages
                
            11. Now we check that dockerfilre is locally working or not
                
                sudo docker build -t chai-and-code-express .

                sudo docker run -it -p 8000:8000 chai-and-code-express 

                http://localhost:8000/health

                http://localhost:8000/


            12. We will host on cloud like AWS, Azure, GCP, etc so we called image registry
                
                docker official image registry is called docker hub
                
                docker - hub.docker.com
                
                AWS ECR - Amazon Elastic Container Registry 
                
                GCP GCR - Google Cloud Container Registry
                
                Azure ACR - Azure Container Registry
 
            13. Login in AWS ECR
                
                Create Private repository - chai-and-code-express
            
            14. Click on repo and then click on view push command
                
            15. Setup aws cli
                
               refer this 
               
                 https://medium.com/@simonazhangzy/installing-and-configuring-the-aws-cli-7d33796e4a7c

            16. Retrieve an authentication token and authenticate your Docker client to your registry. Use the AWS CLI:

                 aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 869935099377.dkr.ecr.ap-south-1.amazonaws.com
            
            17. After the build completes, tag your image so you can push the image to this repository:

            docker tag chai-aur-code-express:latest 869935099377.dkr.ecr.ap-south-1.amazonaws.com/chai-aur-code-express:latest

            18. Run the following command to push this image to your newly created AWS repository:

                docker push 869935099377.dkr.ecr.ap-south-1.amazonaws.com/chai-aur-code-express:latest

            19. Visit aws ecs console and Create clusters using aws Fargate
                  
                chai-and-new-code-cluster

            20. create task definition and create service with fargate serverlesa
                 
                Task -definition family Name - chai-and-new-code-task 
            
                Launch type - Fargate
            
                Operating system/Architecture - Linux/x86_64 (i used this )
            
                 Network mode - awsvpc
            
                 Cpu - 1 vCPU
            
                 Memory - 3 GB    

                 Task role - ecsTAskExecutionrole
            
                 Task Execution role - create new role
            
                 Container DETAILS - chai-and-code-image / container
            
                 Image URI - 869935099377.dkr.ecr.ap-south-1.amazonaws.com/
            
                 chai-aur-code-express:latest
            
                 Container port - 8000 (becuae my container is exposing port 8000)
            
                  Health check - CMD-SHELL,curl -f http://localhost:8000/health || exit 1
            
                  Health check grace period - 30s
            
                 Health check retry count - 3
            
                 Click on create --its created task but you can't delete it and its not chargeable

            21. Click on cluster and then click on services and then click on create service

                 Choose Capacity Provider - Fargate
            
                 Task Definition - chai-and-new-code-task
            
                 Family Name - select created task definition family name

                 Service Name - chai-and-code-service
        
                 Desired task - 1

                 Deployment options - Rolling update

                 Service auto scale - yes

                 Click on Create

            22. After creation, Go to security group and add in bound rule is all tcp with anywhere IPV4.

            23. Click on DNS which u can get from load balancer DNS name

                example : http://chai-aur-code-lb-2079954951.ap-south-1.elb.amazonaws.com
                      
                          http://chai-aur-code-lb-2079954951.ap-south-1.elb.amazonaws.com/health
        
            

