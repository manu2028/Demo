node(){
    try{
        stage("Checkout"){
            sh "git clone https://github.com/manu2028/demo.git -b main"
            sh "ls -ltr"

            dir("demo"){
                sh "ls -ltr"
            }
        }

        stage ("Testing") {
            println "Testing stage"
        }
    }finally{
        deleteDir()
    }
}