pipeline {
  agent any
    stages {
      stage('checkout') {
        steps {
            sh "rm -rf hello-world-war"
          sh "git clone https://github.com/Laava15/hello-world-war.git"
        }
      }
     stage('build') {
        steps {
          sh "docker build -t lavanya1508/hello-world-war:1.0.1 ."
        }
      } 
       stage('publish') {
        steps {
         withCredentials([usernamePassword(credentialsId: '01f82692-363b-4fee-9263-83edd116e5a6', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) { 
        sh "docker login -u ${DOCKER_USERNAME} -p ${DOCKER_PASSWORD}"
           sh "docker push lavanya1508/hello-world-war:1.0.1"
        }

        }
      } 
    }
}
