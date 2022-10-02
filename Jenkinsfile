pipeline {
	agent any 
	stages{
		stage('git-clone'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Kinge-Service', url: 'https://github.com/Kinge-Service/team3-multibuild.git']]])
			}
		}
		stage('git-clone'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Kinge-Service', url: 'https://github.com/Kinge-Service/team3-multibuild.git']]])
			}
		}
		stage('parallel -stage'){
			when {
				branch 'main'
				parallel{
					stage('systemcheck'){
						steps{
							sh ' sudo systemctl status jenkins'
						}
					}
					stage('version-check'){
						steps{
							sh ' cat /etc/os-release'
						}
					}
				}
			}
			stage('parallel-job2'){
				when{
					branch 'develop'
					parallel{
						stage('subjob1'){
							steps{
								echo "Welcome to Kinge Service"
							}
						}
						stage('subjob2'){
							steps{
								sh 'lscpu'
							}
						}
					}
				}
				stage('end of jobs'){
					steps{
						echo " end of all jobs"
					}
				}
			}
		}
	}
}
