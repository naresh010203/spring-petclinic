pipeline {
    agent { label('maven') }
    trigger{ pollSCM('* * * * *') }
    stages {
        stage('vcs') {
            stpes{
                git branch: 'develop',
                url: 'https://github.com/naresh010203/spring-petclinic.git'
            }
        }
        stage('build') {
            sh 'export PATH="/usr/lib/jvm/java-1.17.0-openjdk-amd64/bin:$PATH"'
            sh 'mvnw package'
        }
    }
}