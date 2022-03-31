pipeline {
    agent any
    stages {
        stage('Checkout') {
            when {
                expression {
                    return env.GIT_LOCAL_BRANCH != 'main';
                }
            }
            steps {
                script {                    
                    checkout([
                        $class: 'GitSCM',
                        branches: [[name: '*/**']],
                        extensions: [[$class: 'ChangelogToBranch', options: [compareRemote: 'origin', compareTarget: 'main']]],
                        userRemoteConfigs: [[name: 'origin', url: 'https://github.com/farazxameer/Jenkins_test']]
                    ])
                }
            }
        }
        stage('Build') { 
            steps {
                sh 'printenv'
                sh 'echo Helloooo'
            }
        }
    }
}
