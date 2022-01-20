pipeline {

    agent {
        node {
            label 'default'
        }
    }

    stages {
        stage('git') {
            steps {
                script {
			withCredentials([usernamePassword(credentialsId: 'olivierbri', passwordVariable: 'password', usernameVariable: 'username')]) {
    
					sh """
						ls -l
						ls -l ../
						echo test > file_test
						git add file_test
						git commit -m 'test'
						git push
			}		"""	
                    
                }
            }
        }
    }
}
