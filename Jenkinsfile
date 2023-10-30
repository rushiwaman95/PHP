pipeline{
    agent any
    enviroment{
        stagging_server="3.110.33.101"
    }
    stages{
        stage('Deploy to Remote'){
            steps{
                sh 'scp ${WORKAPACE}/*root@${stagging_server}:/var/www/html'
            }
        }
    }
}
