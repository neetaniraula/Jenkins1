pipeline {
    agent {
        label 'slave-1'
    }
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
