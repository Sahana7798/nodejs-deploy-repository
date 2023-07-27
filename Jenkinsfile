pipeline {
    agent any 
         stages {
            stage ('Git checkout') {
                steps {
                    git branch: 'main', url: 'https://github.com/Sahana7798/React-app.git'
                }
            }
            stage ('Build') {
                steps {
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
            stage ('deploy') {
                steps {
                sshagent(['pvtkey']) {
                 sh 'scp -o StrictHostKeyChecking=no build/** ec2-user@54.172.96.235:/home/ec2-user'
            }
         }
     }
}
}