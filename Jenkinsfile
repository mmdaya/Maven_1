/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any
    tools {
        maven 'maven_tool'
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
                echo 'Build maven package----done ---done'
                echo '----done ---done'
            }
        }
 /*   stage('Maven-Deploy') { 
            steps {
                sh '''
                echo 'Deploying Package into Tomcat server..'
                '''
                script {
                    /* groovylint-disable-next-line LineLength 
                    deploy adapters: [tomcat9(credentialsId: 'Tomcat-Manager-Deploy', path: '',
                    url: 'http://3.7.68.232:8080/')],
                    contextPath: null, war: 'simple-war/target/itdefined-war-1.0.0.war'
                }
            }
        } */
    }
}
