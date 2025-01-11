pipeline {
    agent any
    environment {
        ANSIBLE_USER = 'root' // Replace with the username for the Ansible server
        ANSIBLE_HOST = 'ip-172-31-14-32' // Replace with the hostname or IP of the Ansible server
        SSH_CREDENTIALS_ID = 'ansible-ssh-key' // The ID of the SSH key stored in Jenkins credentials
    }
    stages {
        stage('Run Ansible Playbook') {
            steps {
                // Use SSH agent to provide credentials for the connection
                sshagent(credentials: [env.SSH_CREDENTIALS_ID]) {
                    // Execute the command to run the Ansible playbook on the remote server
                    sh '''
                    ssh -o StrictHostKeyChecking=no $ANSIBLE_USER@$ANSIBLE_HOST "
                        ansible-playbook /home/ubuntu/roles/tomcat.yml -i /etc/ansible/hosts
                    "
                    '''
                }
            }
        }
    }
}

