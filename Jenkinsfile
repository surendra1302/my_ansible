pipeline {
    agent any
    stages {
        stage('Run Ansible Playbook') {
            steps {
                // Run the Ansible playbook
                sh '''
                ansible-playbook -i /home/ubuntu/my_ansible/hosts /home/ubuntu/my_ansible/tomcat.yml
                '''
            }
        }
    }
}
