pipeline {
    agent any
    tools {
        maven 'M2_HOME'
        jdk 'JAVA_HOME'
    }
    stages {
        stage('Build') {
            steps {
                git 'https://github.com/slimenmohamed/devops.git'
                sh 'mvn clean package -DskipTests'
            }
        }
    }
}
