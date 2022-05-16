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
    stage('Deploy to tomcat using playbook') {
      steps {
          ansiblePlaybook credentialsId: 'ansible_id', disableHostKeyChecking: true, installation: 'ansible', inventory: '/home/ec2-user/web-server', playbook: '/home/ec2-user/file01.yml' 
      }
    }
  }
}
