pipeline  {
    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */
        checkout scm
    }
    agent {
       dockerfile true
    }
    stage ('Docker Build') {
        withDockerServer([uri: "tcp://docker-node:2375"]) {
           stages {
              stage('TEST') {
                 steps {
                    sh 'node --version'
                    sh 'yarn --version'
                 }
              }
           }
         }
    }
}
