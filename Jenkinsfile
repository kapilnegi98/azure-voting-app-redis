pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
           bat label: '', script: 'cd'
         }
      }
      stage('Docker') {
         steps {
     bat label: '', script: '''docker images
cd azure-vote
docker build -t jenkins-pipeline .
'''
         }
      }
    
   }
}
