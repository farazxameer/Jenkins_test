pipeline {
    agent any
    stages {
        stage('Checkout') {
            checkout([
                $class: 'GitSCM',
                branches: [[name: '*/main']],
                extensions: [[$class: 'ChangelogToBranch', options: [compareRemote: 'origin', compareTarget: 'main']]],
                userRemoteConfigs: [[name: 'origin', url: 'https://github.com/uiwjs/react-textarea-code-editor']]
            ])
        }
        stage('Build') { 
            steps {
                sh 'echo Helloooo'
            }
        }
    }
}
