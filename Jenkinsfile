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
						git pull --rebase origin main
						# git pull --rebase
						git remote rm origin
						mkdir rep_copie
						cp -r * rep_copie/ --exclude rep_copie
						ls -l
						ls -l ../
						# git config user.name "olivierbri"
						# echo te > file_te
						# git add *
						# git commit -am 'test'
						# git push --repo=https://${username}:${password}@github.com/olivierbri/test.git --set-upstream https://${username}:${password}@github.com/olivierbri/test.git main
					"""	
			}
                }
            }
        }
    }
}
