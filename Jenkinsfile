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
                    emailext (
                        to: 'tema.potema@gmail.com',
                        subject: 'Pipeline Stage Success: Unit and Integration Tests',
                        body: 'Unit and integration tests passed.',
                    )           
                    
                }
                failure {
                    echo 'Unit and integration tests failed.'
                    emailext (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Failure: Unit and Integration Tests',
                             body: 'Unit and integration tests failed.',
                    )
                    
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
                    emailext (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Success: Security Scan',
                             body: 'Security scan passed.',
                    )
                }
                failure {
                    echo 'Security scan failed.'
                    emailext (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Failure: Security Scan',
                             body: 'Security scan failed.',
                    )
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
                    emailext (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Success: Integration Tests on Staging',
                             body: 'Integration tests on staging passed.',
                    )
                }
                failure {
                    echo 'Integration tests on staging failed.'
                    emailext (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Failure: Integration Tests on Staging',
                             body: 'Integration tests on staging failed.',
                    )
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Finalizing the process by deploying the application to a production server, like an AWS EC2 instance, making it accessible to users'
            }
        }
    
    stage('Declarative: Post Actions') {
            steps {
                mail to: 'tema.potema@gmail.com',
                     subject: 'Test Email from Jenkins Pipeline',
                     body: 'This is a manually triggered test email from the Jenkins Pipeline.'
            }
        }
    }
}
