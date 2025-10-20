pipeline {
    agent any
    tools {
        jdk 'JDK21'       // Match exact name in Jenkins
        maven 'Maven3'    // Match exact name in Jenkins
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
        // Updated path to your Tomcat 9 webapps folder
        bat 'copy target\\GalaxyWebApp.war C:\\Users\\Mahak Modi\\Downloads\\apache-tomcat-9.0.111-windows-x64\\apache-tomcat-9.0.111\\webapps /Y'
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
