pipeline {
    agent {
        node {
            label 'Linux-Node-1'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/gajananps/osTicket.git'
            }
        }

	stage('Set Permissions') {
            steps {
		sh 'chmod +x run.sh'
        }
        }

        stage('build docker container') {
            steps {
                sh 'sudo ./run.sh'
            }
        }
		
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }

        failure {
            echo 'Pipeline failed.'
        }

        always {
            echo 'Cleaning up...'
        }
    }
}
