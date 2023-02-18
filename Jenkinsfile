pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'g++ main/sample.cpp -o output'
        build 'PES1UG20CS127-1'
        echo 'Build Successful'
      }
    }
    stage('Test') {
      steps {
        sh './output'
        echo 'Testing Successful'
      }
    }
    stage('Deploy') {
      when {
        expression {
          currentBuild.result == null || currentBuild.result == 'SUCCESS' 
        }
      }
      steps {
        echo 'Deployment Successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
