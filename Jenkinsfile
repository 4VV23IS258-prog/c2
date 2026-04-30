pipeline {
    agent any
    tools {
        maven 'Maven3'
    }
    post {
        always {
            slackSend channel: '#all-vvce',
                      color: currentBuild.currentResult == 'SUCCESS' ? 'good' : 'danger',
                      message: "Build ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}: Check it out at ${env.BUILD_URL}"
        }
    }
    stages {
        stage('CHECKOUT') {
            steps {
            git 'https://github.com/4VV23IS258-prog/c2.git'
            }
        }
        stage('BUILD'){
            steps {
            dir('demo'){
            bat 'mvn clean install'
            }
            }
        }
        stage('TEST') {
            steps {
                dir('demo'){
                    bat 'mvn test'
                }
            }
        }
    }

}