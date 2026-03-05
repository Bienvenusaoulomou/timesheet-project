pipeline {
    agent any
    stages {
        stage('GIT') {
            steps {
                git branch: 'main', url: 'https://github.com/Bienvenusaoulomou/timesheet-project.git'
            }
        }
        stage('COMPILATION') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('ANALYSIS') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.projectKey=timesheet-devops -Dsonar.host.url=http://localhost:9000 -Dsonar.token=sqa_0a02c76678e8f0c1b5a10ddd40fa620ad1ce0b96'
            }
        }
    }
}
