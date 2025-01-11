pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', credentialsId: 'your_github_credentials', url: 'https://github.com/your_username/your_repository.git'
      }
    }
    stage('Execute Ansible playbook') {
      steps {
        ansiblePlaybook(
          playbook: 'path/to/playbook.yml',
          inventory: 'path/to/inventory.ini',
          credentialsId: 'sample-ssh-key',
          extras: '-e parameter="some value"'
        )
      }
    }
