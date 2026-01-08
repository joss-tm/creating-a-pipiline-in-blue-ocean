pipeline {
    agent {
        docker {
            // Исправлен тег образа
            image 'node:18-alpine'
            // Пробрасываем порт (если нужно для тестов)
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                // Установка зависимостей
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                // Убедитесь, что путь и регистр (Jenkins vs jenkins) совпадают!
                sh 'sh ./jenkins/scripts/test.sh'
            }
        }
    }
}
