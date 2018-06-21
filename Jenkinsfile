pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
            	sh 'export JAVA_HOME=\"/opt/jdk1.8.0_171\"'
                sh '/opt/apache-maven-3.5.3/bin/mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}