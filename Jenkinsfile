pipeline {
    agent any
    stages {
        stage('Build') {
            agent any
            steps {
                checkout scm
                sh 'echo Hello world'
                sh '/opt/apache-maven-3.8.1/bin/mvn validate'
            }
        }
        stage('check-git-Secrets') {
            steps {
                sh 'docker pull gesellex/trufflehog'
                sh 'docker run gesellix/trufflehog --json https://github.com/devopssecure/webapp.git > trufflehog'
            }
        }
    }
}
