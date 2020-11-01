pipeline {
  agent any
  stages {
    stage('Development Build') {
      steps {
        echo 'Pull the code from github'
      }
    }

    stage('Smoke Test') {
      steps {
        echo 'Running the smoke tests'
      }
    }

    stage('Acceptance testing') {
      parallel {
        stage('Acceptance testing') {
          steps {
            echo 'Testing phase'
          }
        }

        stage('Functional testing') {
          steps {
            echo 'Running functional scriptsss'
          }
        }

        stage('Performance Testing') {
          steps {
            echo 'Running JMeter scripts'
          }
        }

      }
    }

    stage('Certify by QA') {
      steps {
        echo 'Certified to approve'
      }
    }

  }
}