pipeline{
  agent any
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
                  sh 'docker build -t devopshint/my-app-1.0 .'
                }
            }
     }
}
}
