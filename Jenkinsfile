pipeline{
    agent any

    tools {
         maven 'mvn'
         jdk 'openjdk-11'
    }

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/medhanoo/java-hello-world-with-maven.git']]])
            }
        }
        stage('build'){
            steps{
               sh 'mvn package'
            }
        }
        stage('check jar file location'){
            steps{
                sh 'echo ================================================='
               sh 'ls -r -l *'
               sh 'echo ================================================='
            }
        }
    }
}
