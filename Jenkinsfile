pipeline {
    agent {label 'eks'}

    stages {
        stage('Clone') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/tush6016/eks-exp-1.git']]])
            }
        }
        stage('Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Action') {
            steps {
                echo "Terraform action is --> ${action}"
                sh "terraform ${action} --auto-approve"
            }
        }
    }
}
