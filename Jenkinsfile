pipeline {
         agent any
             stages {
                    stage('checkout') {
                    steps {
                            git branch: 'master', url: 'https://github.com/Mokshi08/Ditiss_Project.git'
             
          }
        }
       
                 stage('Build') {
                 steps {
                     echo 'Hi, Building the code'
                 }
                 }
                 stage('Test') {
                 steps {
                    input('Do you want to proceed?')
                 }
                 }
                stage('Ansible Deploy') {
             
                 sshagent (credentials: ['lynis']) {
                ansiblePlaybook(
                    credentialsId: lynis',
                    inventory: 'hostfile',
                    installation: 'name of the tool specified on the configuration tool screen',
                    limit: '192.168.5.145',
                    playbook: 'initial_step.yaml',
                    
                )
            }
        }
}
}


