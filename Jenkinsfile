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
             
               steps {
                 
              dir('/etc/ansible')
              {
               
              sh 'ansible-playbook initial_step.yaml -i hostfile -K'
               
            }
            }
        }
}
}

ansible-playbook(credentialsId: 'lynis' , inventory: 'hostfile' , playbook: 'initial_step.yaml')


ansiColor('xterm') {
    ansiblePlaybook(
        playbook: 'initial_step.yaml',
        inventory: 'hostfile',
        credentialsId: 'lynis',
        colorized: true)
}

