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
			git credentialsId: 'olivierbri', url: 'git@github.com:olivierbri/monappli.git'
					sh """
						ls -l
						ls -l ../
						echo test > file_test
						git add file_test
						git commit -m 'test'
						git push --set-upstream origin master
					"""	
                    
                }
            }
        }
    }
}
