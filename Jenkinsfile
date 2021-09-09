pipeline {
    agent any
    stages {
        stage ('Dependencies') {
            steps {
                sh 'npm install'
                sh 'sudo apt update'
                sh 'sudo apt install redis-server'
                sh 'sed -i "s/no/systemd/g" /etc/redis/redis.conf'
                sh 'sed -i "s/no/systemd/g" /etc/redis/redis.conf'
                sh 'sudo systemctl restart redis.service'
            }
        }
        stage ('Build') {
            steps {
                echo 'node index.js'
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    
    }
}