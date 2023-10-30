pipeline {
    agent any
    environment {
        staging_server = "65.2.170.155"
    }
        stage('Deploy to Self') {
            steps {
                script {
                    // Remove the existing 'temp' directory if it exists
                    sh 'rm -rf ${WORKSPACE}/temp'
                    // Create a new 'temp' directory in the workspace
                    sh 'mkdir -p ${WORKSPACE}/temp'
                    // Copy project files to the 'temp' directory
                    sh "cp -r ${WORKSPACE}/* ${WORKSPACE}/temp/"
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
