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
						pwd
						ls -l
						ls -l ../
					"""	
                    
                }
            }
        }
    }
}
