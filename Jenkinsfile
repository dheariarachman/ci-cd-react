pipeline {
    agent any

    stages {
        stage('Clone the Repo') {
            steps {
                echo 'Clonning from Github'
                sh 'rm -rf ci-cd-react'
                sh 'git clone https://github.com/dheariarachman/ci-cd-react.git'
            }
        }
        
        stage('Stage 2 - Build Projects') {
            steps {
                dir('ci-cd-react') {
                  sh "npm run build"
                  sh "ls -l"
                }
            }
        }
    }
}
