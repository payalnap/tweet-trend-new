pipeline {
    agent {
        node{
            label 'maven'
        }
    }
environment {
        JAVA_HOME = tool 'JAVA' 
        PATH = "${JAVA_HOME}/bin:/opt/apache-maven-3.9.8/bin:${env.PATH}"

    stages {
        stage("build") {
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage('SonarQube analysis') {
        environment {
            scannerHome = tool 'payal-sonar-scanner'
        }
        steps{
        withSonarQubeEnv('payal-sonarqube-server') {
            sh "${scannerHome}/bin/sonar-scanner"
        }
        }
    }
}
}