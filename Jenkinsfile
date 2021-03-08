pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                sh 'whoami'
                sh 'echo $USER'
                sh 'chmod +x ./flakey-deploy.sh'
                retry(3) {
                    sh './flakey-deploy.sh'
                }
                timeout(time: 3, unit: 'MINUTES') {
                    sh './health-check.sh'
                }
            }
        }
    }
}
