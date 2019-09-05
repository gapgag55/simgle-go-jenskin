pipeline {
  agent any

  stages {
    stage ('Docker') {
      agent { docker { image 'golang' } }

      steps {
        sh 'docker version'
      }
    }

    // stage('Build') {
    //   steps {
    //     sh 'cd ${GOPATH}/src'
    //     sh 'mkdir -p ${GOPATH}/src/github.com/gapgag55/simple-go-jenkins'
    //     sh 'cp -r ${WORKSPACE}/* ${GOPATH}/src/github.com/gapgag55/simple-go-jenkins'
    //     sh 'cp -r ${WORKSPACE}/vendor/* ${GOPATH}/src'
    //     sh 'go clean -cache'
    //     sh 'go build'
    //   }
    // }
  }
}