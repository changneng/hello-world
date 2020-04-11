pipeline {
  agent {
    docker {
      image 'alpine'
    }

  }
  stages {
    stage('BUILD STAGING') {
      when {
        branch pattern: "release-*"
      }
      steps {
        sh 'echo "Deploy to Staging"'
      }
    }
    stage('BUILD ENG') {
      when {
        branch pattern: "master"
      }
      steps {
        sh 'echo "Deploy to Eng"'
      }
    }
  }
}
