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
						echo test file_test
						git add file_test
						git commit -m 'test'
						git push
					"""	
                    
                }
            }
        }
    }
}
