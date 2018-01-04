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
          container('maven') {
            sh 'pwd'
            sh 'ls -al'
            sh 'cd ./helm/spring-boot-web-example'
            sh 'pwd'
            sh 'ls -al'
            sh 'make release'
            sh 'helm install . --namespace staging --name example-release'
          }
        }
      }

  }
}
