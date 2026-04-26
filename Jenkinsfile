pipeline {
    agent any

    stages {
        stage('Récupération du code') {
            steps {
                echo 'Clonage du projet depuis Git...'
                checkout scm
            }
        }

        stage('Compilation') {
            steps {
                echo 'Compilation du projet Maven...'
                bat 'mvn clean compile'
            }
        }

        stage('Tests') {
            steps {
                echo 'Exécution des tests unitaires...'
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging du projet...'
                bat 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Build réussi !'
        }
        failure {
            echo 'Build échoué !'
        }
    }
}
