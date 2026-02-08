pipeline {
    agent any

    environment {
        IMAGE_NAME     = "java-tomcat-app:1.0"
        CONTAINER_NAME = "tomcatapp"
        APP_PORT       = "8081"
    }

    tools {
        jdk 'JAVA_HOME'
        maven 'MAVEN_HOME'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main'
                    url: 'https://github.com/LohadeDarshan/train-reservation.git'
            }
        }
        stage('code validate') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn validate'   // validate the code
                }
            }
        }
    }
}