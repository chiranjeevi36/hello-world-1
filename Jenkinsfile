pipeline {
  agent any
  tools {
      maven 'maven-3.8.5' 
  }
  stages {
    stage('Initialization') {
      steps {
        sh '''
           echo "PATH=${PATH}"
           echo "M2_HOME=${M2_HOME}"
           '''
      }
    }
    stage('Build task') {
      steps {
        sh 'mvn clean package'
      }
    }
  }
}
