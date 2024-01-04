pipeline{
    agent any
    stages {
        stage('Checkout from Git'){
            steps{
                git branch: 'main', url: 'https://github.com/karthikparthiban/EKS_Terraform.git'
            }
        }
        stage('Terraform version'){
             steps{
                 sh 'terraform --version'
             }
        }
        stage('Terraform init'){
             steps{
                 dir('Eks-terraform') {
                      sh 'terraform init'
                   }      
             }
        }
        stage('Terraform validate'){
             steps{
                 dir('Eks-terraform') {
                      sh 'terraform validate'
                   }      
             }
        }
        stage('Terraform plan'){
             steps{
                 dir('Eks-terraform') {
                      sh 'terraform plan'
                   }      
             }
        }
        stage('Terraform apply/destroy'){
             steps{
                 dir('Eks-terraform') {
                      sh 'terraform ${action} --auto-approve'
                   }      
             }
        }
    }
}
