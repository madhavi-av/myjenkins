pipeline {
    agent {
        label 'jenkins-slave '
    }
    stages {
        def mymaven = tool name : "maven3.9.6"
        stage('Clone Repository') {
            steps {
                git 'https://github.com/madhavi-av/myjenkins.git' 
            }
        }

        stage('Maven Build') {
            steps {
                script {
                    mkdir mymaven
                    cd mymaven
                    sh "${mymaven}/bin/mvn clean package"
                }
            }
        }

        stage('Run JAR file') {
            steps {
                script {
                    sh 'java -jar MyApp/target/MyApp-1.0-SNAPSHOT.jar' 
                }
            }
        }
    }
}
