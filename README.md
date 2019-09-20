## Scope 
- There will be 1 bootstrap cloudformation script and 4 pipelines for the CI CD
- The project will follow below steps for the entire CI CD process 
- The project will be using Jenkins 
- The project will use Blue Green Deployment
- The project will use a forked repository for a sample flask application
<https://github.com/lvthillo/python-flask-docker>

### Boostrap Jenkins
Run `bootstrap.yml` and get a Jenkins Server up and running
 
 ### Pipeline 1 - python-flask-docker
  1. Linting 
  2. Build Docker Image
  3. Run Docker Image
  4. Verufy App is ip
  5. Kill & Remove the container

###  Pipeline 2 - Upload Docker Image to AWS ECR
  1. Get Credentials for uploading Image through aws CLI
  2. Tag the Image 
  3. Upload Image to AWS ECR
  
### Pipeline 3 - Create K8s Cluster
  1. Create k8s cluster using AWS EKS using `eksctl` cli
  - `eksctl` uses CloudFormation underneath and will spin up 2 stacks, 1 for k8s & aws bootstrap and 1 for nodegroup
  - This will provision all needed cloud resources
  2. Create the config for "app-clsuter"
  3. Test the k8s cluster 
  4. Set the current context for kubectl to app-cluster
 
### Pipeline 4 - Deploy to K8s Cluster
  1. Create Blue Zone
  2. Deploy to Blue Zone
  3. Deploy to Green Zone
  4. Route to Blue Zone
  5. Decide to Route to Green Zone 
  6. Route to Green Zone 
