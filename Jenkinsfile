pipeline {
         agent any
             stages {
                    stage('checkout') {
                    steps {
                            git branch: 'master', url: 'https://github.com/Mokshi08/Ditiss_Project.git'
             
          }
        }
         stages {
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
                 
              dir('dev/ansible')
              {
               
              sh 'ansible all -m ping -i hostfile'
               
            }
            }
        }
}
}

ansible-playbook(credentialsId: 'lynis' , inventory: 'hostfile' , playbook: 'initial_step.yaml')
}
