pipeline {
    agent any

    stages {
        stage('Git clone') {
            steps {
               git branch: 'master', url: 'https://github.com/aronky/spring-petclinic.git'
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
    }
}
