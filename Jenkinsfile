pipeline{

    agent any
  
    stages{
	
	    stage('Poll')
		{
		
		steps{
		git credentialsId: '62bb76d6-c3c8-42a1-8838-978511d17bce', url: 'https://github.com/sonaliSuchi/CI.git'
		}
		}
		 stage('Build')
           {
             
            steps {
                  
           bat 'mvn -version'
           echo 'maven set'
            }
        }
        stage('Deploy')
                {
				
				steps{
				deploy adapters: [tomcat9(credentialsId: '99179fb5-2453-4ed2-919f-e36ea5dbf9be', path: '', url: 'http://localhost:8085')], contextPath: 'TestCICD-0.0.1', war: '**/*.war'
				}
                }
       
    }
}