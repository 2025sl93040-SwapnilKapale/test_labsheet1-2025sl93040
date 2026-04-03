pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/2025sl93040-SwapnilKapale/labsheet1-2025sl93040.git'
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

                  # Test add
                  assert calculator.add(2,3) == 5, "Add failed: expected 5"

                  # Test multiply
                  assert calculator.multiply(2,3) == 6, "Multiply failed: expected 6"

                  # Test subtract
                  assert calculator.subtract(5,3) == 2, "Subtract failed: expected 2"

                  # Test divide
                  assert calculator.divide(6,3) == 2, "Divide failed: expected 2"

                  # Edge case: divide by zero
                  assert calculator.divide(5,0) is None, "Divide by zero failed"

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
