pipeline {
  agent {
    label "jenkins-maven"
  }

  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh "mvn clean deploy fabric8:build fabric8:push -Ddocker.push.registry=$JENKINS_X_DOCKER_REGISTRY_SERVICE_HOST:$JENKINS_X_DOCKER_REGISTRY_SERVICE_PORT"

//          input id: 'ok', message: 'ok?'

        }
      }
    }
  }
}
