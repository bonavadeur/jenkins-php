pipeline {
    agent none
    stages {
        stage('Clone') {
            agent {label 'master'}
            steps {
                git 'https://github.com/bonavadeur/jenkins-php.git'
            }
        }
        stage('Slave') {
            agent {'slave-1'}
            steps {
                sh 'mkdir testfolder'
            }
        }
    }
}
// node (label: 'master') {
//     git 'https://github.com/bonavadeur/jenkins-php.git'
// }
// node ('slave-1') {
//     sh 'mkdir hello'
// }
