pipeline {
  agent { label 'slave1' }
    stages {
      stage('checkout') {
        steps {
            sh "rm -rf hello-world-war"
          sh "git clone https://github.com/Laava15/hello-world-war.git"
        }
      }
     stage('build') {
        steps {
          sh "mvn clean package"
        }
      } 
    }
}
