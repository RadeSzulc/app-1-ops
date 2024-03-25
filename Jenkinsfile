pipeline {
    agent any
    parameters {
        string(name: 'GREETING', defaultValue: 'Hello', description: 'Custom greeting message')
        choice(name: 'BRANCH', choices: ['master', 'development', 'feature'], description: 'Git branch to build')
        booleanParam(name: 'FULL_BUILD', defaultValue: true, description: 'Perform a full build')
        password(name: 'SECRET', description: 'A secret token')
    }
    stages {
        stage('Initialize') {
            steps {
                echo "Setup initiated..."
            }
        }
        stage('Build') {
            steps {
                echo "${params.GREETING}, starting build on ${params.BRANCH} branch."
                script {
                    if (params.FULL_BUILD) {
                        echo "Performing a full build..."
                    } else {
                        echo "Performing a partial build..."
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying with secret token: ${params.SECRET}"
            }
        }
    }
}
