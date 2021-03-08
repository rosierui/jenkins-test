/*
pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                sh 'whoami'
                sh 'echo $USER'
                sh 'chmod +x ./flakey-deploy.sh'
                sh 'chmod +x ./health-check.sh'
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
*/

pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                sh 'whoami'
                sh 'echo $USER'
                sh 'chmod +x ./flakey-deploy.sh'
                sh 'chmod +x ./health-check.sh'
                timeout(time: 3, unit: 'MINUTES') {
                    retry(5) {
                        sh './flakey-deploy.sh'
                    }
                }
            }
        }
    }
}