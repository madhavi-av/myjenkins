pipeline {
    agent {
        label 'jenkins-slave '
    }
    tools {
        maven 'mymaven'
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/madhavi-av/myjenkins.git' 
            }
        }

        stage('Maven Build') {
            steps {
                script {
                    sh "mvn clean package"
                }
            }
        }

        stage('Run JAR file') {
            steps {
                script {
                    sh 'java -jar /home/ubuntu/workspace/myfirstjenkins/target/MyApp-1.0-SNAPSHOT.jar' 
                }
            }
        }
    }
}
