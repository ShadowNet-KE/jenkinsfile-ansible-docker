node("docker") {    
    stage('Prepare') {
        steps {
//             sh 'python -m pip install -r requirements.txt'
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
}
