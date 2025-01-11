pipeline {
    agent any
    environment {
        ANSIBLE_USER = 'root' // Replace with Ansible server username
        ANSIBLE_HOST = 'ip-172-31-14-32' // Replace with Ansible server hostname/IP
        SSH_CREDENTIALS_ID = 'ansible-ssh-key'
    }
    stages {
        stage('Run Ansible Playbook') {
            steps {
                sshagent(credentials: [env.SSH_CREDENTIALS_ID]) {
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
