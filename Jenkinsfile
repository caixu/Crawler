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

            echo 'always run'
        }
        success{

            docker run -p 9000:8080 -tid --name jenkinstomcat tomcat
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