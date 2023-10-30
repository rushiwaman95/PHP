pipeline {
    agent any
    environment {
        staging_server = "3.110.33.101"
        ssh_credentials = 'SSH'
        remote_path = '/var/www/html'
    }
    stages {
        stage('Deploy to Remote') {
            steps {
                script {
                    sshagent(credentials: [ssh_credentials], ignoreMissing: true) {
                        sh "scp -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null ${WORKSPACE}/* root@${staging_server}:${remote_path}"
                        sh "scp -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null ${WORKSPACE}/* root@${staging_server}:/var/www/html > scp.log 2>&1"

                    }
                }
            }
        }
    }
}
