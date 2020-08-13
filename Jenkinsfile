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
                echo 'Copiando aplicacao para servidor AWS'
                sh 'scp -o StrictHostKeyChecking=no target/Api-Investimentos.jar ubuntu@54.183.177.22:/home/ubuntu'
            }
        }
    } 
}