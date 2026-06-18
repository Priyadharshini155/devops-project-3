pipeline{
    agent any

    stages{

        stage('checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/Priyadharshini155/devops-project-3.git'
            }
        }

        stage('Build Docker Image'){
            steps{
                sh 'docker build -t project3:v1 .'
            }
        }

        stage('Deploy'){
            steps{
               sh 'docker rm -f project3 || true'
               sh 'docker run -d --name project3 -p 8083:80 project3:v1'
            }
        }
    }
}