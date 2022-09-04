pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/bonavadeur/jenkins-php.git'
            }
        }
        stage('Slave pulling') {
            node ('slave-1') {
                echo "hello"
            }
        }
    }
}