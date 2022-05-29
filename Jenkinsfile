pipeline {
    agent { label 'docker' }
    options {
        ansiColor('xterm')
    }
    stages {
        stage('Check Ansible') {
            steps {
                sh 'ansible --version'
            }
        }
        stage('Prepare') {
            steps {
//                 sh 'python -m pip install -r requirements.txt'
//                 sh 'ansible-galaxy install -r requirements.yml'
                sh 'ansible-galaxy role install geerlingguy.pip geerlingguy.docker'
            }
        }
        stage('Run playbook'){
            dir('/etc/ansible/') {
              ansiblePlaybook(
                    // credentialsId: 'cem_dev',
                    playbook: 'docker.yml',
                    extraVars:[
                      hosts: "all"
                ],
             )
            }
        }
        stage('NPM Test') {
            steps {
                sh 'npm --version'
                sh 'node --version'
            }
        }
    }
}
