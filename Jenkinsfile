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
                    sh 'npm install'
                }
                dir('Classrooms') {
                    sh 'npm install'
                }
                dir('client') {
                    sh 'npm install'
                }
                dir('event-bus') {
                    sh 'npm install'
                }
                dir('Post') {
                    sh 'npm install'
                }
            }
        }
        stage('21i1105 Build Docker Images') {
            steps {
                dir('Auth') {
                    sh 'docker build -t drkn123/auth .'
                }
                dir('Classrooms') {
                    sh 'docker build -t drkn123/classrooms .'
                }
                dir('client') {
                    sh 'docker build -t drkn123/client .'
                }
                dir('event-bus') {
                    sh 'docker build -t drkn123/event-bus .'
                }
                dir('Post') {
                    sh 'docker build -t drkn123/post .'
                }
            }
        }
        stage('21i1105 Push Docker Images') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh 'docker login -u $DOCKER_USER -p $DOCKER_PASS'
                    sh 'docker push drkn123/auth'
                    sh 'docker push drkn123/classrooms'
                    sh 'docker push drkn123/client'
                    sh 'docker push drkn123/event-bus'
                    sh 'docker push drkn123/post'
                }
            }
        }
    }
}