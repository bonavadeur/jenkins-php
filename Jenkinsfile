pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/bonavadeur/jenkins-php.git'
            }
        }
    }
    agent {'slave-1'}
    stages {
        stage('Slave pulling') {
            steps {
                echo "hello"
            }
        }
    }
}