pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh '/opt/apache-maven-3.9.9/bin/mvn -B -DskipTests clean package' 
            }
        }
    }
}
