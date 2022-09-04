pipeline {
    agent {label 'master'}
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/bonavadeur/jenkins-php.git'
            }
        }
    }
}
pipeline {
    agent {'slave-1'}
    stages {
        stage('Slave pulling') {
            steps {
                mkdir testfolder
            }
        }
    }
}