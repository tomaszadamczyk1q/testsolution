pipeline {
    agent any
    environment {
    Main_Env = "Welcome to main branch"
    Python = "C:\\\\Users\\Student\\AppData\\Local\\Programs\\Python\\Python310\\python.exe"
    }

    stages {
        stage('Chceck branch') {
            steps {
                echo 'Building..'
                }
        }
        stage('Test code') {
            steps {
                echo 'Testing..'
                bat "${Python} -m pytest"
                
            }
        }
        stage('Run code') {
            steps {
                bat "${Python}  main.py"
            }
        }
        stage('build image') {
            steps {
                echo 'building image....'
                bat 'docker build -t testsolutionpush .'
                bat 'docker run testsolutionpush'
            }
        }
        stage('push image') {
            steps {
                echo 'pushing image....'
                bat 'docker tag testsolutionpush:latest tomekadamczyk1q:fromjenkinspipeline'
                bat 'docker push tomekadamczyk1q:fromjenkinspipelin'
            }
        }
    }
}