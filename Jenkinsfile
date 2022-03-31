pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    echo 'Im outside if condition'
                    if (env.BRANCH_NAME == 'main') {
                        echo 'I only execute on the main branch'
//                         checkout([
//                             $class: 'GitSCM',
//                             branches: [[name: '*/**']],
//                             extensions: [[$class: 'ChangelogToBranch', options: [compareRemote: 'origin', compareTarget: 'main']]],
//                             userRemoteConfigs: [[name: 'origin', url: 'https://github.com/farazxameer/Jenkins_test']]
//                         ])
                    }
                }
            }
        }
        stage('Build') { 
            steps {
                sh 'echo Helloooo'
            }
        }
    }
}
