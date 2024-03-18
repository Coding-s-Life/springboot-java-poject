pipeline {
    agent {
        label   "ZeroToHero"
    }

    tools {
        jdk 'Java17'
        maven 'Maven3'
    }

    environment {
        PATH = "C:\\WINDOWS\\SYSTEM32;"
    }

    stages {
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }
        stage("Checkout from SCM") {
            steps {
                git branch: 'main',  credentialsId: 'github', url: 'https://github.com/Coding-s-Life/springboot-java-poject'
            }
        }
        stage("Maven Validate") {
            steps {
                bat 'mvn validate'
            }
        }
        stage("Maven Compile") {
            steps {
                bat 'mvn compile'
            }
        }
        stage("Maven Test") {
            steps {
                bat 'mvn test'
            }
        }
        stage("Maven Package") {
            steps {
                bat 'mvn package'
            }
        }
        stage("Maven Install") {
            steps {
                bat 'mvn install'
            }
        }
//         stage("Maven Run Artifact") {
//             steps {
//                 bat 'java -jar target/spring-boot-web.jar'
//                 bat 'start http://localhost:8888'
//
//             }
//         }
    }
}