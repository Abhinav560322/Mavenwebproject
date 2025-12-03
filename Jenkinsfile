pipeline {
    agent any
    
    environment {
        MAVEN_HOME = tool name: 'M3', type: 'ToolLocationNodeProperty'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    checkout scm
                    sh "'${MAVEN_HOME}/bin/mvn' clean install"
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' test"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' deploy"
                }
            }
        }
    }

    post {
        always {
        }
    }
}
