#!/usr/bin/env groovy
pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                sh 'chmod +x ./mvnw'
                sh './mvnw clean compile'
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test'
                junit '**/build/test-results/test/*.xml'
            }
        }
        stage('Build') {
            steps {
                sh './mvnw package'
            }
        }
    }
}