pipeline {
    agent any

    tools {
        maven 'maven'
        jdk 'java'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/master']],
                    extensions: [],
                    userRemoteConfigs: [[
                        credentialsId: 'github access',
                        url: 'https://github.com/sreenivas449/java-hello-world-with-maven.git'
                    ]]
                ])
            }
        }
        stage('Build') {
            steps {
                bat 'mvn package'
                // Use 'sh' instead of 'bat' if your agent is not Windows:
                // sh 'mvn package'
            }
        }
    }
}
