pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment{
        PATH = "/opt/apache-maven-3.9.8/bin:$path"
    }

    stages {
        stage('clone-code') {
            steps {
                git branch: 'main', url: 'https://github.com/payalnap/tweet-trend-new.git'
            }
        }
    }
}

