pipeline {
  agent any

  stages {
    stage('Run tests') {
      steps {
        browserstack(credentialsId: '8217f744-65ef-4a29-9b0e-b3d930c85201') {
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