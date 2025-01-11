pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', credentialsId: 'ansible_key', url: 'https://github.com/surendra1302/my_ansible.git'
      }
    }
    stage('Execute Ansible playbook') {
      steps {
        ansiblePlaybook(
          playbook: '/home/ubuntu/roles/tomcat.yml',
          inventory: '/etc/ansibe/hosts',
          credentialsId: 'ansible-ssh-key'
        )
      }
    }
  }
}
