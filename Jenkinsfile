pipeline {
    agent any
    stages {
        stage ('Dependencies') {
            steps {
                sshagent (credentials: ['sherryinstance']) {
                    sh 'ssh -o StrictHostKeyChecking=no ubuntu@18.236.96.234 uptime'
                    echo 'maually done dependicies'
                    sh 'whoami'
                    sh 'cp -r /var/lib/jenkins/workspace/Node-pipeline/ /home/ubuntu/temp/'
                    sh 'scp -r /home/ubuntu/temp ubuntu@18.236.96.234:/home/ubuntu/'
                }
            }
        }
        stage ('Build') {
            steps {
                sh 'npm install'
                sh 'docker-compose up -d --build'
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    
    }
}