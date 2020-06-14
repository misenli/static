pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(credentials: 'aws-static', region: 'ap-northeast-1') {
          sh 'echo "Hello World with AWS creds"'
          s3Upload(file:'index.html', bucket:'cyonemori-publish-bucket', path:'index.html')
        }
      }
    }
  }
}