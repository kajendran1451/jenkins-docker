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
    stage('Docker deployment')
    {
    steps{
   sh 'docker run -d -p 8091:8091 --name tomcattest1 kajendran1451/my-app-1.0 ' 
    }
    }
}
}
