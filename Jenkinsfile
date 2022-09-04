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
    sh 'cd /home/ubuntu20'
    sh 'rsync -aP --delete -e "ssh -i .ssh/bonavadeur" filvr@192.168.101.117:/home/filvr/bonavadeur/jenkins/workspace/jenkins-php-pipeline/ ./jenkins/workspace/jenkins-php-pipeline/'
}
node ('slave-1') { // build and upload artifact to nexus
    sh 'cd /home/ubuntu20/jenkins/workspace/jenkins-php-pipeline'
    sh 'zip code.zip ./*'

}
