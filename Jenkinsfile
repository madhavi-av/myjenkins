pipeline {
    agent {
        label 'jenkins-slave '
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
                    sh 'mvn clean package' 
                }
            }
        }

        stage('Install Java') {
            steps {
                script {
                    sh 'sudo apt-get install -y openjdk-17-jdk' 
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
