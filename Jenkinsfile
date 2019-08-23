diff Environment = "Developement"
pipeline {
   agent any
   stages {
       stage('Git-checkout') {
	       steps {
		           echo "git checkout successfully";
		           git credentialsId: '7ff0883b-5f93-4ad2-8489-50a6a2d195b6', url: 'https://github.com/mannangazi/Kusum.git'
				 }
			}
       stage('compile') {
	       steps {
                   echo "compile successfully";
                   sh label: '', script: 'sh compile.sh'
            }
         }
        stage('junit')  {
            steps {
                    echo "junit successfully";
                    sh label: '', script: 'sh junit.sh'
            }
        }
        stage('deploy') {
            steps {
                    echo " deploy successfully";
                    sh label: '', script: 'sh deploy.sh'
		    echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL} on ${Environment}"
            }
        }
	}
		
}
