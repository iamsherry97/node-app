pipeline {
    agent any
    stages {
        stage ('Dependencies') {
            steps {
                sshagent (credentials: ['sherryinstance']) {
                    sh 'ssh -o StrictHostKeyChecking=no ubuntu@18.236.96.234 uptime'
                    echo 'maually done dependicies'
                    sh 'scp /home/ubuntu/key.pem ubuntu@18.236.96.234:/home/ubuntu/'
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