pipeline {
    agent { label 'MAVEN_JDK8' }
    triggers { pollSCM('* * * * *') }
    tools {
        jdk 'JDK_8'
    }
    stages {
        stage('VCS') {
            steps {
                git url: 'https://github.com/SyedSohail123/july23-jenkins.git',
                    branch: 'declarative'
            }
        }
        stage('Build & Package') {
            steps {
                sh 'export PATH="/usr/lib/jvm/java-8-openjdk-amd64/bin/java:$PATH"'
                sh 'java -version'
                sh 'mvn package'
            }
        }        
    }
}