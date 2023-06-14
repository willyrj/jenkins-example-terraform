pipeline {
  agent { label 'agent-pro-01'}
  options {
    skipDefaultCheckout(true)
  }
  stages{
    stage('clean workspace') {
      steps {
        cleanWs()
      }
    }
    stage('checkout') {
      steps {
        checkout scm
      }
    }         
    stage('Terraform init') {
            steps {
               sh 'terraform init' 
            }
        }
    stage('Terraform apply') {
        steps {
            sh 'terraform apply --auto-approve'
        }
    }   
  }
  post {
    always {
      cleanWs()
    }
  }
}
