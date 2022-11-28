pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'print ttest'
        git(url: 'https://github.com/aeroxavier85/test.git', branch: 'master', changelog: true)
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