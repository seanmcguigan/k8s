pipeline {
  agent {
    kubernetes {
      yamlFile 'kubectl.yaml'
    }
  }
  if(env.BRANCH_NAME == 'master'){
    stages {
      stage('deploy to cms staging') {
        steps {
          container('kubectl') {
            sh 'echo KUBECTL_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}'
            sh '/opt/bitnami/kubectl/bin/kubectl get nodes'
          }
        }
      }
    }
  }
}
