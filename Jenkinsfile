pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout scm
                echo 'Hello World'
                sh 'cat README.md'
            }
        }
    }
}
