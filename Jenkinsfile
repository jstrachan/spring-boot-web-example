pipeline {
  agent {
    label "jenkins-maven"
  }

  stages {
    stage('Build Release') {
      steps {
        container('maven') {
          //sh "mvn clean deploy fabric8:build fabric8:push -Ddocker.push.registry=$JENKINS_X_DOCKER_REGISTRY_SERVICE_HOST:$JENKINS_X_DOCKER_REGISTRY_SERVICE_PORT"
        }
      }
    }
    stage('Deploy Staging') {

      steps {
        dir ('./helm/spring-boot-web-example') {
          container('maven') {
            input id: 'ok', message: 'ok?'
            //sh 'make release'
            //sh 'helm install . --namespace staging --name example-release'
          }
        }
      }
    }
  }
}
