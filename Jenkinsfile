pipeline {
  agent {
    docker {
      image 'alpine'
    }

  }
  stages {
    stage('TEST') {
      steps {
        echo pullRequest.labels
        script {
          if (env.BRANCH_NAME == 'master') {
              env.TARGET = "STAGING"
          } else {
              env.TARGET = "PRODUCTION"
          }
        }
      }
    }
    stage('FINAL') {
      steps {
        sh 'echo "ENV: $TARGET"'
      }
    }
  }
}

