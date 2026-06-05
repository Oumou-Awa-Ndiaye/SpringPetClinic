pipeline {
    agent any

    tools {
        maven 'M3'
    }

    stages {
        stage('Récupération du code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Oumou-Awa-Ndiaye/SpringPetClinic.git'
            }
        }

        stage('Compilation') {
            steps {
                bat 'mvn compile -Djacoco.skip=true'
            }
        }

        stage('Tests') {
            steps {
                bat 'mvn test -Djacoco.skip=true'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package -Djacoco.skip=true -DskipTests'
            }
        }

        stage('Deploy') {
            steps {
                bat 'mvn install -Djacoco.skip=true -DskipTests'
            }
        }
    }
}
