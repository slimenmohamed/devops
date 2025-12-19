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
          stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''
                    mvn sonar:sonar \
                    -Dsonar.projectKey=devops-project \
                    -Dsonar.projectName=devops-project \
                    -Dsonar.host.url=http://192.168.56.10:9000
                    '''
                }
            }
        }
    }
}
