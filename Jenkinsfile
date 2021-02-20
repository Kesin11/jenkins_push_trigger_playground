pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'env'
                sh '''
                     gh api repos/Kesin11/jenkins_push_trigger_playground/commits/${GIT_COMMIT}/statuses \
                     -X POST -F state=pending -F description=trigger
                '''
                checkout scm
                echo 'Hello World'
                sh 'cat README.md'
            }
            post {
                success {
                sh '''
                     gh api repos/Kesin11/jenkins_push_trigger_playground/commits/${GIT_COMMIT}/statuses \
                     -X POST -F state=success -F description=success
                '''
                }
                failure {
                sh '''
                     gh api repos/Kesin11/jenkins_push_trigger_playground/commits/${GIT_COMMIT}/statuses \
                     -X POST -F state=failure -F description=failed
                '''
                }
            }
        }
    }
}
