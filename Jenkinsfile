pipeline {
    agent any

    tools {
       maven 'Apache Maven 3.9.1'
    }

    stages {
        stage('git clone') {
            steps {
                   git branch: 'main', credentialsId: 'github', url: 'https://github.com/YERRAPUREDDYDEEPAK/JENKINS345.git'
            }
        }
		stage('Maven Clean')
		{
		  steps {
		  sh 'mvn clean'
		  }
		}
		stage('Maven Test')
		{
		  steps {
		  sh 'mvn test'
		  }
		}
		stage('Maven compile')
		{
		  steps {
		  sh 'mvn compile'
		  }
		}
	        stage('Code Scan')
		{
		  steps {
		  mvn sonar:sonar -Dsonar.host.url=http://15.206.89.37:9000 -Dsonar.login=a79ab637484ebb36663778b3965729d67a926c42
		  }
		}
		stage('Maven Package')
		{
		  steps {
		  sh 'mvn package'
		  }
		}
		stage('Maven Deploy')
		{
		  steps { 
		  sh 'mvn deploy'
		  }
		}
	        
	}
}
