pipeline {
    agent any
    tools {
        go 'go-1.14'
    }
    environment {
        GO111MODULE = 'on'
    }
	container('builder-go') {
		stages {
			stage('Build') {
				steps {
					sh 'go build'
				}
			}
		}
	}
}