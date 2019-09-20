## Scope 
- There will be 1 bootstrap cloudformation script and 3 pipelines for the CI CD
- The project will follow below steps for the entire CI CD process 
- The project will be using Jenkins 
- The project will use Blue Green Deployment
- The project will use a forked repository for a sample flask application
<https://github.com/lvthillo/python-flask-docker>

### Boostrap Jenkins
Run `bootstrap.yml` and get a Jenkins Server up and running
 
 ### Pipeline 1 
  1. Linting 
  2. Build/Install using Makefile
  3. Verify 
  4. Deploy Image to AWS ECR
  
### Pipeline 2 
  1. Create k8s cluster using AWS EKS using `eksctl` cli
  - `eksctl` uses CloudFormation underneath and will spin up 2 stacks, 1 for k8s & aws bootstrap and 1 for nodegroup
  - This will provision all needed cloud resources
 
### Pipeline 3
  1. Create Blue Zone
  2. Deploy to Blue Zone
  3. Deploy to Green Zone
  4. Route to Blue Zone
  5. Decide to Route to Green Zone 
  6. Route to Green Zone 

### Outro
Plan what your pipeline will look like.
Decide which options you will include in your Continuous Integration phase.
Pick either Jenkins or Jenkins X to use.
Pick a deployment type - either rolling deployment or blue/green deployment.
For the Docker application you can either use an application which you come up with, or use an open-source application pulled from the Internet, or if you have no idea, you can use an Nginx “Hello World, my name is (student name)” application.
