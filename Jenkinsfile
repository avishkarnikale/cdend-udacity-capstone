pipeline {
  agent any 
  stages {
    stage('Get Creds,Tag,Push') {
       steps {
                sh '''#!/bin/bash
                
                        
                        
                     STR=$( aws ecr get-login --no-include-email --region ap-southeast-1 )
                     STR2="sudo "   
                     eval "$STR2$STR"
                     
                     '''
       }
    }
  }
}
