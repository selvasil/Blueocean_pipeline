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
        git(url: 'https://github.com/selvasil/EyeAutomation', branch: 'master')
        bat(script: 'mvn test -DEnvironment=QA', label: 'Script Run in QA env')
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
            echo 'Running functional scripts'
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
        input(message: 'Are u sure to certify?', ok: 'Yes')
      }
    }

  }
}