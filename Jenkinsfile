pipeline {
    agent any
    stages {
        stage ('Dependencies') {
            steps {
                sh 'apt update'
                sh 'apt install nodejs'
                sh 'apt install redis-server'
                sh 'sed -i "s/no/systemd/g" /etc/redis/redis.conf'
                sh 'sed -i "s/no/systemd/g" /etc/redis/redis.conf'
                sh 'systemctl restart redis.service'
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