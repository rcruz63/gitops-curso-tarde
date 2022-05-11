pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World!'
            }
        }
        stage('Test') {
            agent { label "docker-agent" }
            when {
                branch 'PR-*'
            }
            steps {
                sh 'echo "Raul" | ./secreto.sh pepito'
            }
        }
        stage ('secreto'){
            agent { label "docker-agent" }
            steps{
                sh 'echo "secreto" | ./secreto.sh pepito'
            }
        }
    }
}
