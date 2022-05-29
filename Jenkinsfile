node("docker") {    
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
