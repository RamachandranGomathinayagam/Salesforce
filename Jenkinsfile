pipeline {
  agent any
  stages {
    stage('Development') {
      steps {
        echo 'Development build is completed'
      }
    }

    stage('QA  integration testing') {
      parallel {
        stage('QA  integration testing') {
          steps {
            echo 'QA Build is ready'
            git(url: 'https://github.com/RamachandranGomathinayagam/Salesforce', branch: 'master')
            bat 'cd C:\\Users\\Ram\\.jenkins\\workspace\\Salesforce_master\\Salesforce'
            bat 'cd C:\\Users\\Ram\\.jenkins\\workspace\\Salesforce_master\\Salesforce mvn test'
          }
        }

        stage('QA API testing') {
          steps {
            echo 'API testing is completed'
          }
        }

        stage('QA performance Testing') {
          steps {
            echo 'Performance test is completed'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployment is completed'
      }
    }

  }
}