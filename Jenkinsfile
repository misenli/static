pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(credentials: 'aws-static', region: 'ap-northeast-1') {
          sh 'echo "Hello World"'
          s3Upload(file:'index.html', bucket:'cyonemori-publish-bucket', path:'.')
          sh '''
            echo "Multiline shell steps works too"
            ls -lah
          '''
        }
      }
    }
  }
}