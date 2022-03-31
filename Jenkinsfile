pipeline {
    agent any
    stages {
        stage('Test 1') {
            when {
                anyOf {
                    changeset "test1/**"
                    expression {  
                        sh(returnStatus: true, script: 'git diff  origin/main --name-only | grep --quiet "^test1/*"') == 0
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
        stage('Test 1') {
            when {
                anyOf {
                    changeset "test2/**"
                    expression {  
                        sh(returnStatus: true, script: 'git diff  origin/main --name-only | grep --quiet "^test2/*"') == 0
                    }
                }
            }
            steps {
                script {                    
                    echo "Changes in test2 directory"
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
