#!/usr/bin/env groovy
pipeline {
    agent any

    stages {
        stage('Set Executable Flag on Gradlew') {
            steps {
                sh 'chmod +x mvnw'
            }
        }
        stage('Compile') {
            steps {
                sh './mvnw clean compile'
            }
            post {
                success {
                    echo 'Компиляция прошла успешно.'
                }
                failure {
                    echo 'Ошибка на этапе компиляции.'
                }
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test'
            }
            post {
                success {
                    echo 'Тестирование прошло успешно.'
                }
                failure {
                    echo 'Ошибка на этапе тестирования.'
                }
            }
        }
        stage('Build') {
            steps {
                sh './mvnw package'
            }
            post {
                success {
                    echo 'Сборка прошла успешно.'
                }
                failure {
                    echo 'Ошибка на этапе сборки.'
                }
            }
        }
    }
}