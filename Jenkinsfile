def Environment;
node
{
   stages {
       stage('Git-checkout') {
	       steps {
		           echo "git checkout successfully";
		           git credentialsId: '7ff0883b-5f93-4ad2-8489-50a6a2d195b6', url: 'https://github.com/mannangazi/Kusum.git'
				 }
			}
       stage('compile') {
	       steps {
		   Environment = 'Developement'    
                   echo "compile successfully";
                   sh label: '', script: 'sh compile.sh'
		   echo "Welcome to ${Environment} env."
		       
            }
         }
        stage('junit')  {
            steps {
		    Environment = 'QC'   
                    echo "junit successfully";
                    sh label: '', script: 'sh junit.sh'
		    echo "Welcome to ${Environment} env."
            }
        }
        stage('deploy') {
            steps {
		    Environment = 'Production'   
                    echo " deploy successfully";
                    sh label: '', script: 'sh deploy.sh'
		    echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL} on ${Environment}"
		    echo "Welcome to ${Environment} env."
            }
        }
	}
		
}
