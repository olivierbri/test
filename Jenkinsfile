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
						# On met à jour le repo cloné
						git pull --rebase origin main
						
						# On supprime le lien avec la branche distante
						git remote rm origin
						
						# On fait le ménage
						if [ -d rep_copie ]; then rm -r rep_copie; fi
						if [ -d monappli ]; then rm -r monappli; fi
						
						# On archive le contenu du repo
						tar -cvzf archive.tar.gz *
						
						# On créé un repertoire pour copier l'archive
						mkdir rep_copie
						
						# On extrait le contenu de l'archive dans le repertoire
						tar -xvzf archive.tar.gz --directory rep_copie/
						
						# On clone le repo cible
						git clone https://${username}:${password}@github.com/olivierbri/monappli.git
						
						# On copie le contenu du repo source dans le repo cible
						cp -r rep_copie monappli/
						
						# On sauvegarde, commit et push le contenu sur le repo cible
						cd monappli/
						git add *
						git commit -m 'copie'
						git push origin master
						
						
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
