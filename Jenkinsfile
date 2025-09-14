

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/Kiranhuddar/aws.git',
                        credentialsId: 'apps_github'
                    ]]
                ])
            }
        }
                        stage('List Files') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'ls -lrt'
                    } else {
                        bat 'dir'
                    }
                }
            }
        }
    }
}