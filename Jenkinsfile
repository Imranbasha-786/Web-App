pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Imranbasha-786/Web-App.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.109.153.161:8080/')], contextPath: null, war: 'target/*.war'
            }
        }
    }
}
