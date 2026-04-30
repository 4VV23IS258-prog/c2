pipeline {
    agent any
    tools {
        maven 'Maven3'
    }

    stages {
        stage('CHECKOUT') {
            steps {
            git 'repo_link'
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