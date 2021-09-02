pipeline {
    agent {
        label '!windows'
    }

    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
	LD_LIBRARY_PATH = '/opt/openssl/1.0.2u/lib'
    }

    stages {
        stage('Build') {
            steps {
                echo "Database engine is ${DB_ENGINE}"
                echo "DISABLE_AUTH is ${DISABLE_AUTH}"
                echo "LD_LIBRARY_PATH is ${LD_LIBRARY_PATH}"
                sh 'printenv'
            }
        }
    }
}
