pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                dir('prep1') {
                    sh 'ansible-playbook playbooks/ping/ping.yml --syntax-check'
                }
            }
        }
        stage('Deploy') {
            steps {
                dir('prep1') {
                    sh 'ansible-playbook playbooks/ping/ping.yml'
                }
            }
        }
    }
}