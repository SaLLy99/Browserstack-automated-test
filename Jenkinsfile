pipeline {
  agent any

  stages {
    stage('Run tests') {
      steps {
        browserstack(credentialsId: 'a6a239d1-4009-4c65-a527-b2ce8f7c99fd') {
           bat 'mvn test -D sample-test.testng.xml'
        }
      }
    }
  }

  post {
    success {
      browserStackReportPublisher 'automate'
    }
  }
}
