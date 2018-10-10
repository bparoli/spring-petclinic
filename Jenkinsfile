pipeline {
    agent { label 'linux' }
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/bparoli/spring-petclinic.git'
          }
        }
        stage('Build') {
            agent { docker 'maven:3.5-alpine' }
            steps {
                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
    }
}
