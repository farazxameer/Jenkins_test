pipeline {
    agent any
    stages {
        stage('Checkout') {
            when {
                anyOf {
                    changeset "test1/**"
                    expression {  
                        sh(returnStatus: true, script: 'git diff  origin/master --name-only | grep --quiet "^test1/*"') == 0
                    }
                }
//                 expression {
//                     return env.GIT_LOCAL_BRANCH != 'main';
//                 }
            }
            steps {
                script {                    
                    echo "Changes in test1 directory"
                }
            }
        }
        stage('Build') { 
            steps {
                sh 'printenv'
                sh 'echo Hiiii'
            }
        }
    }
}
