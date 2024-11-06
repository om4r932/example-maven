pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh '/opt/apache-maven-3.9.9/bin/mvn -B -DskipTests clean package' 
            }
        }

        stage('Release tag') {
            environment {
                GIT_TAG = "Version-1.$BUILD_NUMBER"
            }
            steps {
                sh 'git config user.name "Omar"'
                sh 'git config user.email "jenkins@om4r932.fr"'
                
                sh 'git tag -a \$GIT_TAG -m \"[Jenkins CI] New Tag\"'
                sh 'git push origin \$GIT_TAG'
            }
        }
    }
}
