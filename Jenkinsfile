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
                sh 'npm test'
            }
        }
        stage ('deploy') {
            steps {
                sshagent(['newone']) {
                    sh 'scp -r -o StrictHostKeyChecking=no build/** ec2-user@18.212.165.117:/home/ec2-user'
            }
        }
    }
    
}
}
