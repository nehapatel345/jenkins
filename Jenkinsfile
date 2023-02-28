pipeline {
  agent any
  
  environment {
        CLOUDSDK_CORE_PROJECT='jenkins-server-project' 
    }
  
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/nehapatel345/jenkins'
      }
    }
    
  
    
    stage('Terraform Init') {
      steps {
        sh 'terraform init'
      }
    }
    
    stage('Terraform Plan') {
      steps {
        sh 'terraform plan'
        // sh 'terraform plan -var app_name=${TF_VAR_app_name} -var env=${TF_VAR_env} -out=tfplan'
      }
    }
    
    stage('Terraform Apply') {
      steps {
        sh 'terraform apply -auto-approve'
        // sh 'terraform apply -auto-approve tfplan'
    }
    
  }
}
}



