pipeline {
    agent any

    stages {
        stage('Build & Run Tests') {
            steps {
                // Para Windows: usar 'bat'
                bat 'mvn clean verify -DskipTests=false'
            }
        }

        stage('Publish Serenity Report') {
            steps {
                publishHTML([
                    allowMissing: false,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: 'target/site/serenity',
                    reportFiles: 'index.html',
                    reportName: 'Serenity Report'
                ])
            }
        }
    }
}
