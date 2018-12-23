pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                retry(3){
                    sh 'echo this is retry'
                }

                timeout(time:3,unit:'SECONDS'){
                    sh 'echo timeout excute'
                }
            }
        }
    }

    post{

        always{

            echo 'This will always run'
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