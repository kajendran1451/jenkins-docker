pipeline{
  agent any
  stages{
    stage('Build'){
          steps{
            sh 'mvn clean install'
          }
       }
    }
   stage('Build Docker Image') {
            steps {
                script {
                  sh 'docker build -t devopshint/my-app-1.0 .'
                }
            }
     }
}
