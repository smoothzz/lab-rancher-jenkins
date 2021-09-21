pipeline {

  environment {
    registry = "192.168.1.81:5000/justme/myweb"
    dockerImage = ""
  }

  agent { label 'kubepod'}

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/smoothzz/lab-rancher-jenkins', branch:"main"
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