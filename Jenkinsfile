pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'env'
                checkout scm
                echo 'Hello World'
                sh 'cat README.md'
            }
        }
    }
}
