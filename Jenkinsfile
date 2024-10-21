pipeline {
    agent {
        node {
            label 'maven' //nodes
        }
    }

    stages {
        stage('Clone-code') {
            steps {
                git branch: 'main', credentialsId: 'maven-server-cred', url: 'https://github.com/HamzaMerdassi55/Spring-app.git'
            }
        }
    }
}
