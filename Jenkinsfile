pipeline{
  agent any
  stages{
    stage('build'){
          steps{
            sh 'mvn clean install'
          }
       }
     stage('Docker Image') {
             steps {
                script {
                  sh 'docker build -t kajendran1451/my-app-1.0 .'
                }
            }
     }
    stage('Docker deployment'){
   sh 'docker run -d -p 8090:8080 --name tomcattest kajendran1451/my-app-1.0 ' 
   }
}
}
