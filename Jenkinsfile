pipeline {
  agent {
    label "jenkins-maven"
  }

  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh 'mvn clean deploy fabric8:build'
//          input id: 'ok', message: 'ok?'

        }
      }
    }
  }
}
