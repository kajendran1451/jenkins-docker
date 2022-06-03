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
          withCredentials([string(credentialsId: 'kajendran1', variable: 'dockerhubpwd')]) {
    sh 'docker login -u kajendran1 -p ${dockerpwd}'
}
          sh 'docker push kajendran1/my-app-1.0 .'
        }
      }
    }
}
}
