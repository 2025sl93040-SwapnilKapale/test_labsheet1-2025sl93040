pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/2025sl93040-SwapnilKapale/test_labsheet1-2025sl93040.git'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Build stage - Python project"'
            }
        }

        stage('Test') {
            steps {
                sh '''
                python3 - <<EOF
import calculator

assert calculator.add(2,3) == 5
assert calculator.multiply(2,3) == 6

print("All tests passed")
EOF
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploy stage running"'
            }
        }
    }
}
