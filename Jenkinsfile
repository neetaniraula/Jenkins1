pipeline {
    agent any
    stages {
        stage('Clone repo') {
            steps {
                git branch: 'main', url: 'https://github.com/spring-projects/spring-petclinic.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Archival') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar, target/surefire-reports/*.xml', followSymlinks: false
            }
        }
    }
}
