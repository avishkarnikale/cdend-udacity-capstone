## Scope 
- There will be 1 bootstrap cloudformation script and 4 pipelines for the CI CD
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

###  Pipeline 2 
  1. Deploy Image to AWS ECR
  
### Pipeline 3 
  1. Create k8s cluster using AWS EKS using `eksctl` cli
  - `eksctl` uses CloudFormation underneath and will spin up 2 stacks, 1 for k8s & aws bootstrap and 1 for nodegroup
  - This will provision all needed cloud resources
 
### Pipeline 4
  1. Create Blue Zone
  2. Deploy to Blue Zone
  3. Deploy to Green Zone
  4. Route to Blue Zone
  5. Decide to Route to Green Zone 
  6. Route to Green Zone 

### Outro
