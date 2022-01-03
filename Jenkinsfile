pipeline {
    agent any

    stages {

        stage('Checkout'){
            steps {
                sh "git clone https://github.com/manu2028/demo.git -b main"
                sh "ls -ltr"

                dir("demo"){
                    sh "ls -ltr"
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building'
             }
        }
        stage('Test'){
            steps{
                echo 'Testing'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying'
            }
        }
    }
}
