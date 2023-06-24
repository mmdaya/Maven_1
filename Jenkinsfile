/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any
    tools {
        maven 'maven-3.9.2'
    }
    stages {
        stage('Maven-Build') {
            steps {
                sh '''
                cd simple-war/
                echo 'Build maven package'
                ls
                mvn clean package
                '''
            }
        }
        stage('Maven-Deploy') {
            steps {
                /* groovylint-disable-next-line DuplicateStringLiteral */
                sh '''
                echo 'Deploying maven package'
                deploy adapters: [tomcat9(credentialsId: 'Tomcat-Manager-Deploy', path: '', url: 'http://3.7.68.232:8080/')], contextPath: null, war: '/simple-war/target/itdefined-war-1.0.0.war'
            }
        }
    }
}
