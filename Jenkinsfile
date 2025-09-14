

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
        stage('stage1') {
            steps {
                echo 'Stage1'
            }
        }
        stage('stage2') {
            steps {
                echo 'stage2'
            }
        }
    }
}