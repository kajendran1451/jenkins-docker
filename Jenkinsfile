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
                  sh 'docker build -t kaj/my-app-1.0 .'
                }
            }
     }
    stage('deploy docker image'){
      steps {
        script {
          withCredentials([string(credentialsId: 'Kajendran1', variable: 'dockerpwd')]) {
    sh 'docker login -u kajendran -p ${dockerpwd}'
}
          sh 'docker push kaj/my-app-1.0 .'
        }
      }
    }
}
}
