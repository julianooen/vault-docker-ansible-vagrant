pipeline {
    agent any
    stages {
        stage('Git clone') {
            steps{
                git branch: 'master', url: 'https://github.com/julianooen/vault-docker-ansible-vagrant.git'
            }
        }
        stage('Ansible') {
            steps {
                sh 'ansible-playbook playbook.yml'
            }
        }
    }
} 