pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the GitHub repository
                git credentialsId: 'AdityaJadhavrao', url: 'https://github.com/AdityaJadhavrao/jenkins-maven-project.git'
            }
        }
        
        stage('Build') {
            steps {
                // Build the Maven project
                sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests if any
                sh 'mvn test'
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the application if needed
                // This can be deploying to an application server or any other deployment process
                // Example: sh 'mvn deploy'
            }
        }
    }

    post {
        success {
            // If the build is successful, you can perform further actions here
            // For example, you can trigger another job or send notifications
            // Example: echo 'Build successful! Triggering downstream job...'
            // Example: build job: 'downstream-job'
        }
        failure {
            // If the build fails, you can perform further actions here
            // For example, you can send notifications or rollback deployments
            // Example: echo 'Build failed! Sending notification...'
            // Example: mail to: 'team@example.com', subject: 'Build Failed', body: 'Build failed for project XYZ'
        }
    }
}
