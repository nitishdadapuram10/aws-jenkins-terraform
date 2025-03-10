pipeline{
    agent any
    tools {
        terraform 'terraform'
    }
    stages{
        stage('checkout from GIT'){
            steps{
               git branch: 'main', credentialsId: 'testpipeline', url: 'https://github.com/nitishdadapuram10/aws-jenkins-terraform.git'
            }
        }
        stage('Terraform Init'){
            steps{
                sh 'terraform init'
            }
        }
        stage('Terraform Plan'){
            steps{
                sh 'terraform plan'
            }
        }
         stage('Terraform Apply'){
            steps{
                sh 'terraform apply --auto-approve'
            }
        }
        // stage('Terraform Destroy'){
        //     steps{
        //         sh 'terraform destroy --auto-approve'
        //     }
        // }
       
    }
}
