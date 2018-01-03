pipeline {
  agent {
    label "jenkins-maven"
  }

  stages {
    stage('Run maven') {
      steps {
        container('maven') {
//          sh 'mvn clean deploy'
//          input id: 'ok', message: 'ok?'
          sh 'mvn -version'
        }
      }
    }
  }
}
