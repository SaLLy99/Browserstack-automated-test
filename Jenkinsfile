pipeline {
  agent any

  stages {
    stage('Run tests') {
      steps {
        browserstack(credentialsId: '64a5f64e-cffa-4bbe-9a71-d3181ce72b96') {
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
