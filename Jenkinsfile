pipeline{
    agent any
   environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }
    stages{
        stage('checkout from GIT'){
            steps{
               git branch: 'main', credentialsId: 'testpipeline', url: 'https://github.com/nitishdadapuram10/aws-jenkins-terraform.git'
            }
        }
        stage('Terraform Init'){
            steps{
                bat 'terraform init'
            }
        }
        stage('Terraform Plan'){
            steps{
                bat 'terraform plan'
            }
        }
         stage('Terraform Apply'){
            steps{
                bat 'terraform apply --auto-approve'
            }
        }
        // stage('Terraform Destroy'){
        //     steps{
        //         sh 'terraform destroy --auto-approve'
        //     }
        // }
       
    }
}
