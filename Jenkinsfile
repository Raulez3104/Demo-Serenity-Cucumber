pipeline {
    agent any

    stages {
        stage('Checkout'){
            steps{
                git 'https://github.com/Raulez3104/Demo-Serenity-Cucumber.git'
            }

        }
        stage('Build & Run Tests') {
            steps {
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
