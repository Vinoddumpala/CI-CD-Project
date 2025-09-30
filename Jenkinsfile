pipeline {
    agent any
    tools {
        maven 'Maven3'
        jdk 'JDK11'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/demo-app.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQubeServer') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                sh '''
                  curl -u admin:password -T target/demo-app.war                   "http://<TOMCAT_HOST>:8080/manager/text/deploy?path=/demo-app&update=true"
                '''
            }
        }
    }
    post {
        success { echo "Build and Deployment Successful!" }
        failure { echo "Build Failed. Please check logs." }
    }
}