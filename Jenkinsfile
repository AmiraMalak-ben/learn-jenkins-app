pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat '''
                    docker run --rm ^
                    -v "%CD%:/workspace" ^
                    -w /workspace ^
                    node:18-alpine ^
                    sh -c "rm -rf build && node --version && npm --version && npm ci && npm run build"
                '''
            }
        }
    }
}
