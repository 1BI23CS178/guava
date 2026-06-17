pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/1BI23CS178/MyMavenGuavaApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Create Source File') {
            steps {
                sh 'echo "data will be copied!" > source.txt'
            }
        }

        stage('Run Application') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
            }
        }

        stage('Verify Output') {
            steps {
                sh 'cat destination.txt'
            }
        }
    }
}
