pipeline {
    agent any
    stages {
        stage('Download code') {
            steps {
                git 'https://github.com/iExad/example-playbook.git'
            }
        }
        stage('Execute ansible') {
            steps {
                sh 'ansible-galaxy install -p $WORKSPACE -r requirements.yml'
                sh 'ansible-playbook ./site.yml -i ./inventory/prod.yml'
            }
        }
    }
}
