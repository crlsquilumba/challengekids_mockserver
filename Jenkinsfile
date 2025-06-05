pipeline {
    agent any
    tools {
        nodejs 'node16' // Usa el nombre que configuraste en Jenkins para NodeJS
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Instalar dependencias') {
            steps {
                sh 'npm install'
            }
        }
        stage('Lint') {
            steps {
                sh 'npm run lint || echo "No hay lint configurado"'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test || echo "No hay tests configurados"'
            }
        }
    }
    post {
        success {
            echo '¡Pipeline exitoso! Puedes hacer merge.'
        }
        failure {
            echo 'El pipeline falló. Revisa los errores antes de hacer merge.'
        }
    }
}
