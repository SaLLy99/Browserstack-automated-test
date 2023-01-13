pipeline {
  agent any

  stages {
    stage('Run tests') {
      steps {
        browserstack(credentialsId: '4d640553-cd95-47a8-88e0-0468106adc80') {
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
