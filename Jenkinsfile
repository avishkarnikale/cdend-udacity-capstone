pipeline {
  agent any 
  stages {
    stage('Get Creds') {
       steps {
                sh "( aws ecr get-login --no-include-email --region ap-southeast-1 )"
       }
    }
    stage('Tag Image') {
       steps {
                sh 'sudo docker tag cdend-uda-avish-capstn:latest 423966027140.dkr.ecr.ap-southeast-1.amazonaws.com/cdend-uda-avish-capstn:latest'
       }
    }
    stage('Upload to ECR') {
       steps {
                sh 'sudo docker push 423966027140.dkr.ecr.ap-southeast-1.amazonaws.com/cdend-uda-avish-capstn:latest'
       }
    }
  }
}
