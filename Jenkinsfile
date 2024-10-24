pipeline {
    agent {
        node {
            label 'maven' //nodes
        }
    }

environment {
    PATH = "/opt/apache-maven-3.9.9/bin:$PATH"
}
    stages {
        stage("build") {
            steps {
                sh 'mvn clean deploy'
            }
        }
    stage('SonarQube analysis') {
    environment {
      scannerHome = tool 'hamzaoui-sonar-scanner'
    }
    steps {
    withSonarQubeEnv('hamzaoui-sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
   
  }    
}
}
