pipeline {
    agent any
    tools {
        jdk 'JDK 21'
        maven 'Maven'
    }
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building GalaxyWebApp...'
                bat 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying GalaxyWebApp...'
                bat 'copy target\\GalaxyWebApp.war C:\\apache-tomcat-10.0.27\\webapps /Y'
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check console output.'
        }
    }
}
