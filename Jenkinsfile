pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
    durabilityHint('PERFORMANCE_OPTIMIZED')
    disableConcurrentBuilds()
  }
  stages{
    stage('build') {
      steps {
        sh 'echo "Hello Hoangg saved in S3" > hello.txt'
      }
    }
    stage('archive') {
      steps {
        archiveArtifacts(artifacts: '**/*.txt', followSymlinks: false)
      }
    }
  }
}
