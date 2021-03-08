pipeline {
    agent any
    stages {
        stage('mw_build') {
            steps {
                sh 'echo "mw_build finished"'
            }
        }
        stage('deploy') {
            steps {
                sh 'echo "deploy"; exit 0'
            }
        }
        stage('custom_stage_name') {
            steps {
                sh 'echo "test passed!"; exit 0'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {  // executed before success or failure block
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
