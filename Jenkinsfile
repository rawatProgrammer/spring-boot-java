pipeline {
    agent none
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
            agent any
            steps {
                sh 'docker run gesellix/trufflehog --json https://github.com/rawatProgrammer/spring-boot-java > trufflehog'
                sh 'cat trufflehog'
            }
        }
    }
}
