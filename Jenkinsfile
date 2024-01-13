pipeline {
    agent {
        label  'MAVEN' 
    }
    options { timeout(time: 30, unit: 'MINUTE') }
    triggers { pollSCM('* * * * *') }
    stages {
        stage('git-clone') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git'
                    branch: 'main'
            }
            
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}