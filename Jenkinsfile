pipeline {
    agent any
    environment {
        VERCEL_TOKEN = credentials('VERCEL_TOKEN')
    }
    tools {
        nodejs 'NodeJS'
    }
    stages {
        stage("Install") {
            steps {
                sh 'npm install'
            }
        }
        stage("Test") {
            steps {
                echo "Running tests..."
            }
        }
        stage("Build") {
            steps {
                sh 'npm run build'
            }
        }
       stage("Deploy") {
    steps {
        sh "npx vercel --prod --yes --token=${VERCEL_TOKEN}"
    }
}
    }
}