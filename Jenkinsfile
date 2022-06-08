pipeline{
  agent any
  environment{
    dockerimage = ''
    registry = 'kajendran1451/kaj'
  }
  stages{
    stage('checkout'){
          steps{
            git branch: 'main', url: 'https://github.com/kajendran1/jenkins-docker.git'
          }
       }
 
    stage('Build'){
          steps{
            sh 'mvn clean install'
          }
       }
   stage('Docker Image') {
            steps {
                script {
                  sh 'docker image = docker.build registry'
                }
            }
     }
  }
}

