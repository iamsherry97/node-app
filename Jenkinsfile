pipeline {
    agent any
    environment {
        value = 'prod'
    }
    stages {
        stage ('Dependencies') {
            steps {
                sshagent (credentials: ['sherryinstance']) {
                    sh 'ssh -o StrictHostKeyChecking=no ubuntu@18.236.96.234 uptime'
                    echo 'maually done dependicies'
                    sh 'whoami'
                    sh 'sleep 3'
                    sh 'scp -r /var/lib/jenkins/workspace/Node-pipeline ubuntu@18.236.96.234:/home/ubuntu/app-"$BUILD_ID"-"$value"'
                }
            }
        }
        stage ('Build') {
            steps {
                sshagent (credentials: ['sherryinstance']) {
                    sh 'ssh -v ubuntu@18.236.96.234 bash node-script.sh'
                }
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    
    }
}