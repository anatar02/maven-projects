pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'export M2_HOME=/usr/local/Cellar/maven/3.5.3/libexec'
                sh 'mvn clean package'
            }
             post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war' 
                }
            }
        }
    }
}
