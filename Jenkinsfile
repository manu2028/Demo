pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                git branch: 'main', credentialsId: 'jenkins-credentials', url: 'https://github.com/manu2028/JenkinsPipelineDemo.git'
            }
        }
    }
}
