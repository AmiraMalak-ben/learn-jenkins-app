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
                    sh -c "npm config set fetch-retries 5 && npm config set fetch-retry-mintimeout 20000 && npm config set fetch-retry-maxtimeout 120000 && npm config set fetch-timeout 600000 && node --version && npm --version && npm ci --no-audit --no-fund && npm run build"
                '''
            }
        }
    }
}
