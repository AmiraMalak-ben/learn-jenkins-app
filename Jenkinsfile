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
                    sh -c "chmod -R u+rwX /workspace && rm -rf build && ls -la && node --version && npm --version && npm ci && npm run build"
                '''
            }
        }
    }
}

