pipeline {
    agent any
    stages {
        stage ('Dependencies') {
            steps {
 //               sh 'sudo -S apt update'
 //               sh 'sudo -S apt install nodejs'
 //               sh 'sudo -S apt install redis-server'
 //               sh 'sudo -S sed -i "s/no/systemd/g" /etc/redis/redis.conf'
  //              sh 'sudo -S sed -i "s/no/systemd/g" /etc/redis/redis.conf'
 //               sh 'sudo -Ssystemctl restart redis.service'
                echo 'maually done dependicies'
            }
        }
        stage ('Build') {
            steps {
                sh 'npm install'
                timeout (time: 300 ,unit: 'SECONDS') {
                    sh 'docker-compose up --build'
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