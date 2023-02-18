pipeline {
    agent any
    
    tools {
        nodejs 'Node 18.12.1'
    }

    stages {
        stage('Cloning Git') {
            steps {
                git 'https://github.com/gem-shubhamkumar/wdio-orange-hrm-ts.git'
            }
        }
        
        stage('Install dependencies') {
            steps {
                bat 'npm install'
            }
        }
        
        stage('Run Test') {
            steps {
                bat 'npm run smoke'
            }
        }

        post{
            always{
                echo "========always========"
                mail bcc: '', body: 'Sample Mail', cc: 'skg11786@gmail.com', from: '', replyTo: '', subject: 'WDIO Jenkins Report', to: 'device.test1420@gmail.com'
            }
        }
        
    }
}