pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
           bat label: '', script: 'cd'
         }
      }
       stage('parallel') {
          parallel{
             stage('stage1'){
                steps{
                timeout(time: 8, unit: 'SECONDS') 
                }
             }
             stage('stage2'){
                steps{
                timeout(time: 3, unit: 'SECONDS') 
                }
             }
      }
       }
 
      stage('docker push'){
         steps{
            echo '$WORKSPACE'
            dir('$WORKSPACE/azure-vote') {
            script{
               
               
                  docker.withRegistry('https://hub.docker.com/', 'dockerhub') {

        def customImage = docker.build("kapilnegi/conferenceapp:latest")

        /* Push the container to the custom Registry */
        customImage.push()
    // some block
                  }     
             
            }
         
         }
      }
      }
    
   }
   post {
      always{
         echo 'hello everyone'
      }
   }
}

