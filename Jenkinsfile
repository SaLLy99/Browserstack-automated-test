pipeline {
  agent any

  stages {
    stage('Run tests') {
      steps {
        browserstack(credentialsId: 'b59572cc-e3ee-46f4-ae4c-3143838a9b45') {
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
