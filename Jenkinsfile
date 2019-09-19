pipeline {
  agent any 
  stages {
    stage('Get Creds') {
       steps {
                sh '''#!/bin/bash

                      STR=$( aws ecr get-login --no-include-email --region ap-southeast-1 )
                      STR2="sudo "   
                      eval "$STR2$STR"
                   '''
             }
     }
     stage('Tag Image4ECR') {
        steps {
                      sudo docker tag cdend-uda-avish-capstn:latest 423966027140.dkr.ecr.ap-southeast-1.amazonaws.com/cdend-uda-avish-capstn:latest
        }
     }
     stage('Upload Image2ECR') {
        steps {               
                      sudo docker push 423966027140.dkr.ecr.ap-southeast-1.amazonaws.com/cdend-uda-avish-capstn:latest
        }            
    }
  }
}
