pipeline{
	agent any
		stages{
			stage('Checkout Source'){
				steps{
					echo 'Checking for Git repo source code'
					git branch:'main',url:'https://github.com/SaiVarshitha123-marojuvarsh/jenkins-master-slave.git'
				}
			}
			stage('Install Dependencies'){
				steps{
					echo 'Installing depencies'
					bat 'mvn clean install -DskipTests'
				}
			}
			stage('Build and Testing'){
				steps{
					echo 'Build and testing'
					bat 'mvn test'
				}
			}
			stage('Archive Artifact'){
				steps{
					echo 'Archiving the artificats'
					archiveArtifacts artifacts:'**/target/*.jar',fingerprint:true
				}
			}
		}
		post{
			success{
				echo 'Build success'
			}
			failure{
				echo 'Build failed'
			}
		}
}
				

