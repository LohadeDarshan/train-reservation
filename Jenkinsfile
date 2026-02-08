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
                git branch: 'main', url: 'https://github.com/LohadeDarshan/train-reservation.git'
            }
        }
        stage('code validate') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn validate'   // validate the code
                }
            }
        }
        stage('code compile') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn compile'   // compile
                }
            }
        }
        stage('code test') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn test'   // test
                }
            }
        }
        stage('code build and scan') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                    withSonarQubeEnv(credentialsId: 'sonar-token', installationName: 'sonar') {
                        sh 'mvn clean package org.sonarsource.scanner.maven:sonar-maven-plugin:sonar'// validate + compile + test + package
                    }
                }
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }
    }
}