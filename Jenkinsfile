pipeline {
    agent any

    environment {
        TOMCAT_HOME = "C:\\apache-tomcat-9.0.73" // Change this to your Tomcat 9 installation path
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/mehek89/GalaxyWebApp.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building GalaxyWebApp..."
                bat 'mvn clean package'  // Windows command to build with Maven
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying GalaxyWebApp to Tomcat 9..."
                // Copy the WAR file to Tomcat's webapps folder
                bat "copy target\\GalaxyWebApp.war %TOMCAT_HOME%\\webapps\\"
            }
        }
    }

    post {
        success { 
            echo 'Pipeline completed successfully!' 
        }
        failure { 
            echo 'Pipeline failed. Check console output!' 
        }
    }
}
