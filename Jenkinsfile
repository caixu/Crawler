pipeline {
    agent any

    environment{
        DISABLE_AUTH    = 'true'
        DB_ENGING       = 'sqlite'
    }
    stages {
        stage('Test'){
            steps{
                sh 'printenv'
            }
        }
    }

    post{

        always{

            mail to:'1105823913@qq.com',
                 subject:"jenkins test",
                 body:"this is just a jenkins test"
        }
        success{

            echo 'this will run only if successful'
        }
        failure{
            echo 'this will run only if failed'
        }
        unstable{
            echo 'this will run only if the run was marked as unstable'
        }
        changed{
            echo 'this will run only if the state of the Pipeline has changed'
            echo 'For example,if the Pipeline was previously failing but is now fuccessful!'
        }
    }
}