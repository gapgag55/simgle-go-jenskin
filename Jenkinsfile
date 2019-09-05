pipeline {
  agent { docker { image 'golang' } }

  stages {
    stage('Build') {
      steps {
        sh 'cd ${GOPATH}/src'
        sh 'mkdir -p ${GOPATH}/src/YOUR_PROJECT_DIRECTORY'
        sh 'cp -r ${WORKSPACE}/* ${GOPATH}/src/YOUR_PROJECT_DIRECTORY'
        sh 'cp -r ${WORKSPACE}/vendor/* ${GOPATH}/src'
        sh 'go clean -cache'
        sh 'go build'
      }
    }

    stage('Push image') {
      steps {
        script {
          withDockerRegistry(
            credentialsId: 'docker-credential',
            url: 'https://index.docker.io/v1/') {
            dockerImage.push()
          }
        }
      }
    }
  }
}