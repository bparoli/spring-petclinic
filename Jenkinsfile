pipeline{
	agent {docker 'maven:3.5-alphine' }
	stages{
    	stage ('Checkout') {
        	steps {
            	git 'https://github.com/bparoli/spring-petclinic.git'
          	}
        }
        stage ('Build') {
        	steps {
            	sh 'mvn clean package'
               	junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
	}
}

