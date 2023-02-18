pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh "make -C main"
        echo 'Building folder'
      }
    }
    stage('Test') {
      steps {
         sh "/var/jenkins_home/workspace/pes1ug20cs158/main/hello_exec"
         echo 'Testing completed'
      }
      
    }
    stage('Deploy') {
      steps {
        echo 'Deployed'
      }
    }
  }
  post {
    always {
      echo 'Deployment pending'
    }
    success {
      echo 'Pipeline succeeded!'
    }
    failure {
      echo 'Pipline failed!'
    }
  }
}
