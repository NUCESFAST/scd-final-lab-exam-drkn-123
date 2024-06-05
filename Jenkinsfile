pipeline {
    agent any
    stages {
        stage('21i1105 Checkout') {
            steps {
                git 'https://github.com/NUCESFAST/scd-final-lab-exam-drkn-123.git'
            }
        }
        stage('21i1105 Install Dependencies') {
            steps {
                dir('Auth') {
                    bat 'npm install'
                }
                dir('Classrooms') {
                    bat 'npm install'
                }
                dir('client') {
                    bat 'npm install'
                }
                dir('event-bus') {
                    bat 'npm install'
                }
                dir('Post') {
                    bat 'npm install'
                }
            }
        }
        stage('21i1105 Build Docker Images') {
            steps {
                dir('Auth') {
                    bat 'docker build -t drkn123/auth .'
                }
                dir('Classrooms') {
                    bat 'docker build -t drkn123/classrooms .'
                }
                dir('client') {
                    bat 'docker build -t drkn123/client .'
                }
                dir('event-bus') {
                    bat 'docker build -t drkn123/event-bus .'
                }
                dir('Post') {
                    bat 'docker build -t drkn123/post .'
                }
            }
        }
    }
}