pipeline {
    agent any
    environment {
        staging_server = "65.2.170.155"
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
