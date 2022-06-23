@Library("raghu-test@main") _
pipeline {
    agent any
    tools {
        go-1.9.2 '1.18.3'
    }
    stages {
        stage('Checkout') {
            steps {
              deleteDir()
              echo "Checking out....."
              checkout scm
            }
        }
        stage('Build App') {
            when {
                expression { params.BRANCH != 'develop' }
            }         
            steps {
                gobuild()
            }
        }
    }
}
