pipeline {
    agent any
    stages {
        stage('build') {
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
}