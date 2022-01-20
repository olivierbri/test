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
					sh """
						ls -l
						ls -l ../
						echo test > file_test
						git add file_test
						git commit -m 'test'
						git push
					"""	
                    
                }
            }
        }
    }
}
