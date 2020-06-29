pipeline {
  agent {
    docker {
      image 'golang:latest-alpine'
    }
  }

  stages {
    // first stage installs node dependencies and Cypress binary
    stage('Build') {
      steps {
        // there a few default environment variables on Jenkins
        // on local Jenkins machine (assuming port 8080) see
        // http://localhost:8080/pipeline-syntax/globals#env
        echo "Running build ${env.BUILD_ID} on ${env.JENKINS_URL}"
        sh 'go build'
      }
    }
  }
}