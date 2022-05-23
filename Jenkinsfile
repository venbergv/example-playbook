pipeline {
    agent {
        node {
            label 'ansible_docker'
            }
        }
    stages {
        stage('Get code from GitHub') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/venbergv/example-playbook.git'
            }
        }
        stage('Run ansible') {
            steps {
                sh 'ansible-galaxy install -p $WORKSPACE -r requirements.yml'
                sh 'ansible-playbook $WORKSPACE/site.yml -i $WORKSPACE/inventory/prod.yml'
            }
        }
    }
}
