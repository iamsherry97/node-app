pipeline {
    agent any
    stages {
        stage ('Dependencies') {
            steps {
                sh 'sudo apt update'
                sh 'sudo apt install nodejs'
                sh 'sudo apt install redis-server'
                sh 'sed -i "s/no/systemd/g" /etc/redis/redis.conf'
                sh 'sed -i "s/no/systemd/g" /etc/redis/redis.conf'
                sh 'sudo systemctl restart redis.service'
            }
        }
        stage ('Build') {
            steps {
                sh 'npm install'
                sh 'node index.js'
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    
    }
}