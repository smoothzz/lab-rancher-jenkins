pipeline {

  agent { label 'kubepod'}

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/smoothzz/lab-rancher-jenkins'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}