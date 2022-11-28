pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'print ttest'
        sh 'sh run_build_script.sh'
      }
    }

    stage('Linux test') {
      parallel {
        stage('Linux test') {
          steps {
            echo 'RUN LINUX  tests'
            sh 'sh run_linux_tests.sh'
          }
        }

        stage('Windows Tests') {
          steps {
            echo 'Run Windows tests'
          }
        }

      }
    }

    stage('Deploy Staging') {
      steps {
        echo 'Deploy to staging environment'
        input 'k to deploy to production?'
      }
    }

    stage('Deploy Production Stage') {
      steps {
        echo 'Deploy to Prod'
      }
    }

  }
}