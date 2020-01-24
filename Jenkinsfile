pipeline {
         agent any
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
                 stage('Deploy') {
                 parallel {
                            stage('Deploy start ') {
                           steps {
                                echo "Start the deploy .."
                           }
                           }
                            stage('Deploying now') {
                            agent {
                                    docker {
                                            reuseNode true
                                            image ‘HardenedSystem’
                                           }
                                    }

                              steps {
                                echo "Docker Created"
                              }
                           }
                           }
                           }
}
}

ansible-playbook(credentialsId: 'lynis' , inventory: 'hostfile' , playbook: 'initial_step.yaml')
