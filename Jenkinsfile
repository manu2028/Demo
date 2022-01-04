node(){
    def build_number = env.BUILD_NUMBER
    def version = "1.0.${build_number}"
    try{
        stage("Checkout"){
            sh "git clone https://github.com/manu2028/demo.git -b main"
            sh "ls -ltr"

            dir("demo"){
                sh "ls -ltr"
            }
        }
        dir("demo"){
            stage ("Testing") {
                sh "./gradlew build"
            }

            stage ("Build automation") {
                sh "./gradlew assemble"
            }

            stage("Build Management"){
                println "Work in progress"
            }

            stage("Deployment"){
                // Stop tomcat
                sh "/Users/manognadasari/Documents/apache-tomcat-9.0.56/bin/shutdown.sh"
                 sh "/Users/manognadasari/Documents/apache-tomcat-9.0.56/webapps/rm demo"

                // Remove old files



                // Copy new WAR file

                sh "/Users/manognadasari/Downloads/cp -R demo webapps "


                // Start tomcat
                                sh "/Users/manognadasari/Documents/apache-tomcat-9.0.56/bin/startup.sh"


            }
        }



    }finally{
        deleteDir()
    }
}