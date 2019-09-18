Jenkinsfile (Declarative Pipeline)
pipeline {
    agent { docker { image 'node:10.16.3' } }
    stages {
        stage('build') {
            steps {
            	sh 'echo "Hello World"'
                sh 'npm --version'
            }
        }
    }
}