pipeline {
    agent any

    stages {
        stage('Git clone') {
            steps {
               git branch: 'main', url: 'https://github.com/aronky/spring-petclinic.git'
            }
        }
    
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://18.207.206.191:8080/')], contextPath: 'path', war: '**/*.war'         }
        }
    }
}
