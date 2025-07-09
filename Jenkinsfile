pipeline {
    agent { label 'agent-1' }

    environment {
        ANSIBLE_FORCE_COLOR = "true"
        ANSIBLE_HOST_KEY_CHECKING = "False"
    }

    stages {
        stage('Run Ansible Playbook') {
            steps {
                sh '''
                    ansible-playbook -i inventory.ini playbook.yml
                '''
            }
        }
    }

    post {
        success {
            echo "Nginx deployed successfully!"
        }
        failure {
            echo "Deployment failed."
        }
    }
}
