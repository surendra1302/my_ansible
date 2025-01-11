pipeline {
    agent any
    stages {
        stage('Run Ansible Playbook') {
            steps {
                // Run the Ansible playbook
                sh '''
                ansible-playbook -i /path/to/inventory /path/to/playbook.yml
                '''
            }
        }
    }
}
