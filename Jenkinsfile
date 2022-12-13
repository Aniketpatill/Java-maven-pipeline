pipeline {
   agent any
   tolls {
     maven 'M2_HOME'
    }
    stages{
      stage('checkout the project')
       steps{
        git branch: 'main', url: 'https://github.com/Aniketpatill/Java-maven-pipeline.git'
       }
      }
      stage('build'){
        steps {
          sh 'mvn clean compile'
        }
      }
    }
      post {
         success{
            slackSend channel: 'dedevops-pipeline-demo', message: 'pipeline Built Successfully'
         }
         failure {
            slackSend channel: 'dedevops-pipeline-demo', message: 'pipeline Failed'
         }
      }
   }
