pipeline {
    agent any
    tools {
        go 'go-1.14'
    }
    environment {
        GO111MODULE = 'on'
    }
    stages {
		container('builder-go') {
			stage('Build') {
				steps {
					sh 'go build'
				}
			}
		}
    }
}