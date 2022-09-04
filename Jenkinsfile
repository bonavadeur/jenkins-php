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
// }///
node (label: 'master') { // master pulls code from github
    git 'https://github.com/bonavadeur/jenkins-php.git'
}
node ('slave-1') { // slave-1 pulls code from master
    sh 'rsync -aP --delete -e "ssh -i /home/ubuntu20/.ssh/bonavadeur" filvr@192.168.101.117:/home/filvr/bonavadeur/jenkins/workspace/jenkins-php-pipeline/ /home/ubuntu20/jenkins/workspace/jenkins-php-pipeline/'
}
node ('slave-1') { // build and upload artifact to nexus
    sh 'zip ./workspace/jenkins-php-pipeline/code.zip ./workspace/jenkins-php-pipeline/*'
}
