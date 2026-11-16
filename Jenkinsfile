pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat '''
                    docker run --rm ^
                    -v "%CD%:/workspace" ^
                    -v npm-cache:/root/.npm ^
                    node:18-alpine ^
                    sh -c "mkdir -p /app && cp -r /workspace/. /app/ && cd /app && npm ci --no-audit --no-fund && npm run build && cp -r build /workspace/build"
                '''
            }
        }
    }
}
