pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World!'
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
