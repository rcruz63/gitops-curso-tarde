pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World!'
            }
        }
        stage{
            agent docker-agent
            steps{
                sh 'echo "secreto" | ./secreto.sh pepito'
            }
        }
    }
}
