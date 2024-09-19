pipeline {
    agent any
    environment {
        AWS_DEFAULT_REGION = 'us-east-1' // Replace with your AWS region
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID') // Use your Jenkins credentials
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }
    stages {
        stage('Checkout') {
            steps {
                 git branch: "main', url: 'git@github.com:AhmedEmbaby-git/Terraform-Jenkins.git", credentialsId: "jenkinskey"
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
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}

