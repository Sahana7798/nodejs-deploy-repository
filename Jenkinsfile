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
                sh 'npm start'
            }
        }
        stage ('deploy') {
            steps {
                sshagent(['newone']) {
                    sh 'scp -r -o StrictHostKeyChecking=no build/** ec2-user@3.85.125.66:/home/ec2-user'
            }
        }
    }
    
}
}
