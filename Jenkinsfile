pipeline {
    agent any  
    tools {
        maven 'Maven'  
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/sumanthr27/MyMavenWebApp-Test-CICD.git'
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
        stage('Deploy WAR') {
            steps {
                sh 'cp target/MymavenWebApp-test.war /opt/tomcat/webapps/'
            }
        }    
    }
post {
        success {
            echo 'Build  successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
