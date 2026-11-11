pipeline {
    agent any
    tools {
        maven "M310"
    }
    
    stages {
        stage("hello") {
            steps {
                echo 'running in dev branch!!'
            }
        }
        
        stage("echo version") {
            steps {
                sh 'echo print mvn version'
                sh 'mvn -version'
            }
        }
        
        stage("build") {
            steps {
                // git branch: 'main', changelog: false, poll: false, url: 'https://github.com/codingwarrior-cz/jenkins-hello-world.git'
                sh "mvn clean package -DskipTests=true"
            }
        }
        
        stage("Unit test") {
            steps {
                 sh "mvn test"
            }
        }
    }
}
