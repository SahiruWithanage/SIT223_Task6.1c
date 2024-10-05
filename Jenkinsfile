pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using a build automation tool like Maven or Gradle to compile and package the code.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
            post {
                always {
                    script {
                        // Send email with log at the end of Unit and Integration Tests stage
                        emailext(
                            to: 'hesh.zsg@gmail.com',  // Replace with the specified email address
                            subject: "Unit and Integration Tests - ${currentBuild.currentResult}",
                            body: """<p>The Unit and Integration Tests stage has ${currentBuild.currentResult.toLowerCase()}.</p>
                                     <p>Attached is the full console output for this stage.</p>""",
                            attachLog: true  // Attaches the full console log
                        )
                    }
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code using a tool like SonarQube.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
            }
            post {
                always {
                    script {
                        // Send email with log at the end of Security Scan stage
                        emailext(
                            to: 'hesh.zsg@gmail.com',  // Replace with the specified email address
                            subject: "Security Scan - ${currentBuild.currentResult}",
                            body: """<p>The Security Scan stage has ${currentBuild.currentResult.toLowerCase()}.</p>
                                     <p>Attached is the full console output for this stage.</p>""",
                            attachLog: true  // Attaches the full console log
                        )
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to a staging server, such as an AWS EC2 instance.'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
            }
            post {
                always {
                    script {
                        // Send email with log at the end of Integration Tests on Staging stage
                        emailext(
                            to: 'hesh.zsg@gmail.com',  // Replace with the specified email address
                            subject: "Integration Tests on Staging - ${currentBuild.currentResult}",
                            body: """<p>The Integration Tests on Staging stage has ${currentBuild.currentResult.toLowerCase()}.</p>
                                     <p>Attached is the full console output for this stage.</p>""",
                            attachLog: true  // Attaches the full console log
                        )
                    }
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to a production server, such as an AWS EC2 instance.'
            }
        }
    }
}
