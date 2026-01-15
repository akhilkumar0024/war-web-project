pipeline {
    agent any
    stages {
        stage('Clone Stage') {
            steps {
                echo 'Git checkout...'
                git branch: 'jenkinsAssignment3', url: 'https://github.com/akhilkumar0024/war-web-project.git'
            }
        }
        stage('Build Stage') {
            steps {
                echo 'Building...'
                sh 'mvn clean package'
            }
        }
        stage('Deploy to tomcat') {
            steps {
                echo 'Deploying to Tomcat...'
                sh '''
                curl -u admin:admin123 -T target/*.war http://localhost:8081/manager/text/deploy?path=/myapp&update=true
                echo "Deployed Successfully"
                '''

            }
        }   
    }
}
