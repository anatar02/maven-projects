pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    ArchiveArtifacts artifacts: '**/target/*.war' 
                }
            }
        }
    }
}
