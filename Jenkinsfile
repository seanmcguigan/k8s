pipeline {
  agent {
    kubernetes {
      yamlFile 'kubectl.yaml'
    }
  }
  stages {
    stage('deploy to master') {
      steps {
        script {
          if (env.BRANCH_NAME == 'master') {
            container('kubectl') {
              sh 'echo KUBECTL_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}'
              sh '/opt/bitnami/kubectl/bin/kubectl get nodes'
              sh "echo ${env.BRANCH_NAME}"
            }
          }
        }
      }
    }
    stage('deploy to develop') {
      steps {
        script {
          if (env.BRANCH_NAME == 'development') {
            container('kubectl') {
              sh 'echo KUBECTL_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}'
              sh '/opt/bitnami/kubectl/bin/kubectl get nodes'
              sh "echo ${env.BRANCH_NAME}"
            }
          }
        }
      }
    }           
  }
}

