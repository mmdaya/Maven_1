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
    }
}