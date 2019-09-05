pipeline {
  agent { docker { image 'golang' } }

  stages {
    stage('Build') {
      steps {
        sh 'cd ${GOPATH}/src'
        sh 'mkdir -p ${GOPATH}/src/github.com/gapgag55/simple-go-jenkins'
        sh 'cp -r ${WORKSPACE}/* ${GOPATH}/src/github.com/gapgag55/simple-go-jenkins'
        sh 'cp -r ${WORKSPACE}/vendor/* ${GOPATH}/src'
        sh 'go clean -cache'
        sh 'go build'
      }
    }
  }
}