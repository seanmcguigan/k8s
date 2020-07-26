 pipeline {
  agent {
    kubernetes {
      yamlFile 'kubectl.yaml'
    }
  }
  stages {
    stage('deploy') {
      steps {
        container('kubectl') {
          sh 'echo KUBECTL_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}'
          sh '/opt/bitnami/kubectl/bin/kubectl version'
        }
      }
    }
  }
}
// pipeline {
//   agent {
//     kubernetes {
//       yamlFile 'kubectl.yaml'
//     }
//   }
//   stages {
//     stage('Run maven') {
//       steps {
//         sh 'set'
//         sh "echo OUTSIDE_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}"
//         container('maven') {
//           sh 'echo MAVEN_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}'
//           sh 'mvn -version'
//         }
//         container('busybox') {
//           sh 'echo BUSYBOX_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}'
//           sh '/bin/busybox'
//         }
//       }
//     }
//   }
// }