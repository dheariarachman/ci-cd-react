pipeline {
  agent any

  stages {
    stage('Clone the Repo') {
      steps {
        checkout scm
      }
    }
    
    stage('Stage 2 - Build Projects') {
        steps {
            // dir('ci-cd-react') {
            //   sh "npm install"
            //   sh "npm run build"
              sh "ls -l"
            // }
        }
    }

    // stage('clear bucket') {
    //   steps {
    //     script {
    //       withAWS(region:'ap-southeast-1', credentials:'aws-credentials-learn') {
    //         sh 'aws s3 ls'
    //         sh 'aws s3 rm s3://ci-cd-react --recursive'
    //         sh 'aws s3 sync build/ s3://ci-cd-react'
    //       }
    //     }
    //   }
    // }
  }
}
