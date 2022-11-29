pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        echo 'print ttest'
        sh 'sudo docker run -idt -p 8080:80 apache_latest'
      }
    }

    stage('Linux test') {
      parallel {
        stage('Linux test') {
          steps {
            echo 'RUN LINUX  tests'
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