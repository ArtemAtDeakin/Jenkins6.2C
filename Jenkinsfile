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
                    script {
                        currentBuild.rawBuild.getLogFile().renameTo(new File("jenkins-log.txt"))
                    }
                    mail (
                        to: 'tema.potema@gmail.com',
                        subject: 'Pipeline Stage Success: Unit and Integration Tests',
                        body: 'Unit and integration tests passed.',
                        attachmentsPattern: '**/jenkins-log.txt'
                    )           
                    
                }
                failure {
                    echo 'Unit and integration tests failed.'
                    script {
                        currentBuild.rawBuild.getLogFile().renameTo(new File("jenkins-log.txt"))
                    }
                    mail (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Failure: Unit and Integration Tests',
                             body: 'Unit and integration tests failed.',
                             attachmentsPattern: '**/jenkins-log.txt'
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
                    script {
                        currentBuild.rawBuild.getLogFile().renameTo(new File("jenkins-log.txt"))
                    }
                    mail (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Success: Security Scan',
                             body: 'Security scan passed.',
                             attachmentsPattern: '**/jenkins-log.txt'
                    )
                }
                failure {
                    echo 'Security scan failed.'
                    script {
                        currentBuild.rawBuild.getLogFile().renameTo(new File("jenkins-log.txt"))
                    }
                    mail (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Failure: Security Scan',
                             body: 'Security scan failed.',
                             attachmentsPattern: '**/jenkins-log.txt'
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
                    script {
                        currentBuild.rawBuild.getLogFile().renameTo(new File("jenkins-log.txt"))
                    }
                    mail (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Success: Integration Tests on Staging',
                             body: 'Integration tests on staging passed.',
                             attachmentsPattern: '**/jenkins-log.txt'
                    )
                }
                failure {
                    echo 'Integration tests on staging failed.'
                    script {
                        currentBuild.rawBuild.getLogFile().renameTo(new File("jenkins-log.txt"))
                    }
                    mail (
                             to: 'tema.potema@gmail.com',
                             subject: 'Pipeline Stage Failure: Integration Tests on Staging',
                             body: 'Integration tests on staging failed.',
                             attachmentsPattern: '**/jenkins-log.txt'
                    )
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
