#!groovy

@Library('github.com/ayudadigital/jenkins-pipeline-library@v6.3.0') _

// Initialize global config
cfg = jplConfig('mapfre-gitpos-laboratorio-jenkins', 'bash', '', [email: 'example@example.com'], 'main')

pipeline {
    agent any

    stages {
        stage ('Initialize') {
            steps  {
                jplStart(cfg)
            }
        }
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
