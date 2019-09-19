pipeline {
  agent any 
  stages {
    stage('Get Creds,Tag,Push') {
       steps {
                sh '''#!/bin/bash

                      STR=$( aws ecr get-login --no-include-email --region ap-southeast-1 )
                      STR2="sudo "   
                      eval "$STR2$STR"
                      sudo docker tag cdend-uda-avish-capstn:latest 423966027140.dkr.ecr.ap-southeast-1.amazonaws.com/cdend-uda-avish-capstn:latest
                      sudo docker push 423966027140.dkr.ecr.ap-southeast-1.amazonaws.com/cdend-uda-avish-capstn:latest
                     
                     '''
       }
    }
  }
}
