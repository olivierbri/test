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
						git checkout -b test
						echo test > file_test
						git add file_test
						git commit -m 'test'
						git checkout master
						git push origin test
					"""	
                    
                }
            }
        }
    }
}
