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

        stage('check'){
            steps{
                input "dose the staging environment look ok?"
            }
        }

        stage('Deploy'){
            steps{
                sh 'echo this is deploy'
            }
        }
    }

    post{

        always{

            echo 'always run'
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