pipeline {
  agent any

  stages {
    
    stage('Stage - Build Projects') {
        steps {
          sh "npm install"
          sh "npm run build"
          sh "ls -l"
        }
    }

    stage('clear bucket') {
      steps {
        script {
          withAWS(region:'ap-southeast-1', credentials:'aws-credentials-learn') {
            sh 'aws s3 ls'
            sh 'aws s3 rm s3://ci-cd-react --recursive'
            sh 'aws s3 sync build/ s3://ci-cd-react'
          }
        }
      }
    }
  }

  post {
    cleanup {
        /* clean up our workspace */
        deleteDir()
        /* clean up tmp directory */
        dir("${workspace}@tmp") {
            deleteDir()
        }
        /* clean up script directory */
        dir("${workspace}@script") {
            deleteDir()
        }
    }
  }
}
