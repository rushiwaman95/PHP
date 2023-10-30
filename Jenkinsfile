pipeline {
    agent any
    environment {
        staging_server = "3.110.33.101"
    }
    stages {
        stage('Deploy to Remote') {
            steps {
                sh "scp ${WORKSPACE}/* root@${staging_server}:/var/www/html"
            }
        }
    }
}
