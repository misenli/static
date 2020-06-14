pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(credentials: 'aws-static', region: 'ap-northeast-1') {
          sh 'tidy -q -e *.html'
          s3Upload(file:'index.html', bucket:'cyonemori-publish-bucket', path:'index.html')
        }
      }
    }
  }
}