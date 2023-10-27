pipeline{
    agent any
    environment{
        stagging_server="65.2.170.155"
    }
    stages{
        stage('Deploy to Remote'){
            steps{
                sh 'scp ${WORKAPACE}/*root@${stagging_server}:/var/www/html'
            }
        }
    }
}
