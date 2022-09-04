// pipeline {
//     agent none
//     stages {
//         stage('Clone') {
//             agent {label 'master'}
//             steps {
//                 git 'https://github.com/bonavadeur/jenkins-php.git'
//             }
//         }
//         stage('Slave') {
//             agent ('slave-1')
//             steps {
//                 sh 'mkdir testfolder'
//             }
//         }
//     }
// }
node (label: 'master') {
    git 'https://github.com/bonavadeur/jenkins-php.git'
}
node ('slave-1') {
    sh 'rsync -aP --delete -e "ssh -i /home/ubuntu20/.ssh/bonavadeur" filvr@192.168.101.117:/home/filvr/bonavadeur/jenkins/workspace/jenkins-php-pipeline/ /home/ubuntu20/jenkins/workspace/jenkins-php-pipeline/'
}
