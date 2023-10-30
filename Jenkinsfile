pipeline {
    agent any
    environment {
        staging_server = "65.2.170.155"
    }
    stages {
        stage('Deploy to Self') {
            steps {
                script {
                    
                    sh "scp -r ${WORKSPACE}/* /home/ec2-user"
                }
            }
        }
        stage('Deploy to Remote') {
            steps {
                script {
                    sh "scp -r ${WORKSPACE}/* root@${staging_server}:/var/www/html/"
                }
            }
        }
    }
}
