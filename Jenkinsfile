pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Replace with your Git repository URL
                git 'https://github.com/adivaida/baibichelbit.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image and tag it as 'myapp:latest'
                    docker.build("myapp:latest")
                }
            }
        }

        stage('Run Tests') {
            steps {
                // Run tests inside the Docker container (assumes `npm test` is the test command)
                sh 'docker run --rm myapp:latest npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the app by running it in a container on port 3000
                sh 'docker run -d -p 3000:3000 myapp:latest'
            }
        }
    }
}

