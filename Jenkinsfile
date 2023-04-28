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
		  sh 'mvn sonar:sonar -Dsonar.host.url=http://3.110.218.116:9000 -Dsonar.login=53fd1f77845d4ef57bdb8fed4c19ae02b7c538df'
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
