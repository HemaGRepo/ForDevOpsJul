pipeline {
  agent any
  stages {
    stage('SetUp') {
      steps {
        echo 'Setting Up Environment'
      }
    }
    stage('EmployeeBuild') {
      parallel {
        stage('Build1') {
          steps {
            bat 'cd EMS/src'
          }
        }
        stage('Compile') {
          steps {
            bat 'javac Employee.java'
          }
        }
        stage('Execute') {
          steps {
            bat 'java Employee'
          }
        }
        stage('Report') {
          steps {
            bat 'Employee build successful....'
          }
        }
      }
    }
    stage('TaxBuild') {
      parallel {
        stage('Build2') {
          steps {
            bat 'cd TaxMS/src'
          }
        }
        stage('Compile') {
          steps {
            bat 'javac TaxInfo.java'
          }
        }
        stage('Execute') {
          steps {
            bat 'java TaxInfo'
          }
        }
        stage('Report') {
          steps {
            echo 'Tax Data Available'
          }
        }
      }
    }
    stage('Test') {
      steps {
        echo 'Test Successful...'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}