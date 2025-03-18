pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-username/html-webpage.git'
            }
        }

        stage('Package WAR') {
            steps {
                sh '''
                mkdir -p webapp
                cp index.html webapp/
                jar -cvf sample-webpage.war -C webapp/ .
                '''
            }
        }

        stage('Archive WAR File') {
            steps {
                archiveArtifacts artifacts: 'sample-webpage.war', fingerprint: true
            }
        }
    }
}
