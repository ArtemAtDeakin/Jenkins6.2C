pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Compiling and packaging the code using a build automation tool like Maven or Gradle'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Executing unit tests to verify individual components and integration tests to ensure compatibility between components using JUnit'
            }
            post {
                success {
                    echo 'Unit and integration tests passed.'
                    emailext body: 'Unit and integration tests passed.',
                             subject: 'Pipeline Stage Success: Unit and Integration Tests',
                             to: 'tema.potema@gmail.com'
                }
                failure {
                    try {
    emailext body: 'Unit and integration tests failed.',
             subject: 'Pipeline Stage Failure: Unit and Integration Tests',
             to: 'email@gmail.com'
} catch (Exception e) {
    echo "Error sending email: ${e.getMessage()}"
}

                    echo 'Unit and integration tests failed.'
                    emailext body: 'Unit and integration tests failed.',
                             subject: 'Pipeline Stage Failure: Unit and Integration Tests',
                             to: 'tema.potema@gmail.com'
                }
            }
            
        }

        stage('Code Analysis') {
            steps {
                echo 'Applying code analysis tools like SonarQube or Checkstyle to ensure code quality and adherence to industry standards'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Conducting security scans with tools like OWASP Dependency Check or Snyk to identify potential vulnerabilities in the code'
            }
            post {
                success {
                    echo 'Security scan passed.'
                    emailext body: 'Security scan passed.',
                             subject: 'Pipeline Stage Success: Security Scan',
                             to: 'tema.potema@gmail.com'
                }
                failure {
                    echo 'Security scan failed.'
                    emailext body: 'Security scan failed.',
                             subject: 'Pipeline Stage Failure: Security Scan',
                             to: 'tema.potema@gmail.com'
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to a staging environment, such as an AWS EC2 instance, for further testing before production using'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Performing integration tests in the staging environment to validate the application in a production-like setting using JMeter'
            }
            post {
                success {
                    echo 'Integration tests on staging passed.'
                    emailext body: 'Integration tests on staging passed.',
                             subject: 'Pipeline Stage Success: Integration Tests on Staging',
                             to: 'tema.potema@gmail.com'
                }
                failure {
                    echo 'Integration tests on staging failed.'
                    emailext body: 'Integration tests on staging failed.',
                             subject: 'Pipeline Stage Failure: Integration Tests on Staging',
                             to: 'tema.potema@gmail.com'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Finalizing the process by deploying the application to a production server, like an AWS EC2 instance, making it accessible to users'
            }
        }
    }
}
