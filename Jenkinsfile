pipeline {
    agent any

    environment {
        IMAGE_NAME = "hello-java-basic"
        TAG = "latest"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git(
                    branch: 'main',
                    url: 'https://github.com/oren1984/hello-java-repo.git',
                    credentialsId: 'your-jenkins-credential'  // ודא שהמזהה תואם
                )
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$TAG .'
            }
        }

        stage('Docker Run') {
            steps {
                sh 'docker run --rm $IMAGE_NAME:$TAG'
            }
        }
    }
}
