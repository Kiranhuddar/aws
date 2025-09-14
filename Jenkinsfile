

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
                    def files = []
                    def count = 0
                    dir('.') {
                        files = findFiles(glob: '*')
                        count = files.size()
                    }
                    echo "Total files: ${count}"
                    echo "Files:"
                    files.each { f ->
                        echo "${f.path}"
                    }
                }
            }
        }
    }
}