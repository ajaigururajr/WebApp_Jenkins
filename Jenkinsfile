pipeline {
  agent none
  stages {
    stage('Dev Build') {
      steps {
        echo 'Deploy Dev Build'
      }
    }

    stage('Dev Maven') {
      steps {
        echo 'Deploy to Maven'
      }
    }

    stage('QA Deploy') {
      steps {
        echo 'Deploy to QA'
        echo 'Notify to QA by email'
      }
    }

    stage('QA Tests') {
      parallel {
        stage('QA Tests') {
          steps {
            echo 'Start test after QA Deploy'
          }
        }

        stage('Web/UI Test') {
          steps {
            echo 'Pull a code'
            echo 'Run a Tests'
          }
        }

        stage('API test') {
          steps {
            echo 'Code Pull'
            echo 'Run a test'
          }
        }

      }
    }

    stage('QA Certify') {
      steps {
        echo 'Manual Certify'
        input 'Do you want to Certify'
      }
    }

    stage('UAT Deploy') {
      steps {
        echo 'Deploy to UAT'
      }
    }

    stage('UAT Certify') {
      steps {
        echo 'Certify to UAT'
        input 'Do you want to Certify UAT'
      }
    }

    stage('Prod Deploy') {
      steps {
        echo 'Deploy to Prod'
      }
    }

    stage('End') {
      steps {
        echo 'Done'
      }
    }

  }
}