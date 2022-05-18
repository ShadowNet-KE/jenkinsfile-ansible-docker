node {    
    stage('Run playbook'){
        dir('/etc/ansible/') {
          ansiblePlaybook(
                credentialsId: 'cem_dev',
                playbook: 'Ansible-Playbook-Docker-Vars.yml',
                extraVars:[
                  hosts: "all",
                  servicename: "${servicename}",
                  replica: "${replica}",
                  functions: "${functions}"
            ],
         )
        }
    }
}
