pipeline {
    agent {label 'master'}
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/bonavadeur/jenkins-php.git'
            }
        }
        stage('Slave') {
            agent {'slave-1'}
            steps {
                mkdir testfolder
            }
        }
    }
}