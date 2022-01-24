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
						if [ -d rep_copie ]; then rm -r rep_copie; fi
						tar -cvzf archive.tar.gz *
						mkdir rep_copie
						tar -xvzf archive.tar.gz --directory rep_copie/
						ls -l
						ls -l rep_copie/
						git clone https://github.com/olivierbri/monappli.git
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
