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
                pwd
                cd ./target/
                '''
                echo 'Build maven package----done ---done'
                echo '----done ---done'
            }
        }
   stage('Maven-Deploy') { 
            steps {
                sh '''
                echo 'Deploying Package into Tomcat server..'
                pwd
                cd simple-war/target/
                pwd
                ls
                '''
                script {
                    /* groovylint-disable-next-line LineLength */
                    deploy adapters: [tomcat9(credentialsId: 'tomcat-manager', path: '',
                    url: 'http://18.191.242.81:8081/')],
                    contextPath: '/itdefined-war-1.0.0', 
                    onFailure: false, 
                    war: 'Maven1/simple-war/target/itdefined-war-1.0.0.war'
                }
            }
        }
    }
}
