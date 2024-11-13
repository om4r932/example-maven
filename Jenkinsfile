pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
                sh '/opt/apache-maven-3.9.9/bin/mvn -B -DskipTests clean package' 
            }
        }

        stage('Release tag') {
            environment {
                GIT_TAG = "Version-1.$BUILD_NUMBER"
            }
            steps {
              
                sh 'git tag -a \$GIT_TAG -m \"[Jenkins CI] New Tag\"'
                sh 'git push origin \$GIT_TAG'
            }
        }
    }
}
