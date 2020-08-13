pipeline {
    agent none
    stages {
        stage('Test') {
            agent any
            steps {
                echo 'Executando teste'
                sh './mvnw test'
            }
        }
        stage('Build') {
            agent any
            steps {
                echo 'Construindo projeto'
                sh './mvnw package -DskipTests'
                sh 'mv target/Api-Investimentos-*.jar target/Api-Investimentos.jar'
            }
        }
        stage('Deploy') {
            agent any
            steps {
                echo 'Publicando aplicacao'
                sh 'echo "Hello world"'
            }
        }
    } 
}