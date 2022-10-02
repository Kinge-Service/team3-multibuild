pipeline {
	agent any 
	stages{
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
