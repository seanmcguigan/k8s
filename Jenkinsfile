 pipeline {
  agent {
    kubernetes {
      yamlFile 'kubectl.yaml'
    }
  }
  stages {
    stage('deploy') {
      steps {
        sh "echo OUTSIDE_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}"
        container('kubectl') {
          sh 'echo KUBECTL_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}'
          sh '/opt/bitnami/kubectl/bin/kubectl version'
        }
      }
    }
  }
}