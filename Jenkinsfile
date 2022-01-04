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
                 sh "rm -rf /Users/manognadasari/Documents/apache-tomcat-9.0.56/webapps/demo*"

                // Remove old files



                // Copy new WAR file

                sh "mv build/libs/demo-0.0.1-SNAPSHOT.war /Users/manognadasari/Documents/apache-tomcat-9.0.56/webapps/demo.war"


                // Start tomcat
                                sh "/Users/manognadasari/Documents/apache-tomcat-9.0.56/bin/startup.sh"


            }
        }



    }finally{
        deleteDir()
    }
}