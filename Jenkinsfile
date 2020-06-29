pipeline {
  agent {
    docker {
      image 'golang:1.14-alpine'
    }
  }
  environment { 
      HOME = '.'
      ENV_VAR_PSRNL = 'HI! This is the ENV VAR'
  }

  stages {
    stage('Build') {
      steps {
        // there a few default environment variables on Jenkins
        // on local Jenkins machine (assuming port 8080) see
        // http://localhost:8080/pipeline-syntax/globals#env
        echo "Running build ${env.BUILD_ID} on ${env.JENKINS_URL}"
        sh 'go build'
      }
    }
    stage('Test') {
      steps {
        // there a few default environment variables on Jenkins
        // on local Jenkins machine (assuming port 8080) see
        // http://localhost:8080/pipeline-syntax/globals#env
        echo "Running Tests"
        echo "The environment variable for this stage is: ${ENV_VAR_PSRNL}"
        sh 'go tests ./... -coverprofile=coverage.txt'
      }
    }
  }
}