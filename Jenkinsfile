#!/usr/bin/env groovy
pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                sh 'chmod +x ./mvnw'
                sh './gradlew clean classes'
            }
        }
        stage('Test') {
            steps {
                sh './gradlew test'
                junit '**/build/test-results/test/*.xml'
            }
        }
        stage('Build') {
            steps {
                sh './gradlew war'
            }
        }
    }
}