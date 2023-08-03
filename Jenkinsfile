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
                sshagent(['newone']) {
                    sh 'scp -r -o StrictHostKeyChecking=no build/** ec2-user@52.207.216.177:/mnt/website/html'
            }
        }
    }
    
}
}
