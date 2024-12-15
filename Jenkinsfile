pipeline {
    agent {
        label "jenkins-agent"
    }

    tools {
        maven "maven3.9.9"
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/**/*.jar'
            }
        }
    }
}
