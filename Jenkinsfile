pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Compile') {
            steps {
                sh 'javac HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                sh 'java HelloWorld | tee output.txt'
            }
        }
        stage('Verify') {
            steps {
                sh 'grep -q "Hello, World!" output.txt'
                echo 'Output verified: Hello, World! was printed.'
            }
        }
    }
}
