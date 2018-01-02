pipeline {
  agent {
    label "jenkins-maven"
  }

  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh 'mvn clean install deploy'
        }
      }
    }
  }
}
