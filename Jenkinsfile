pipeline {
    agent any
    tools {
        maven 'Maven3'
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