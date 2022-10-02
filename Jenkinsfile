pipeline {
	agent any 
	stages{
		stage('git-clone'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Kinge-Service', url: 'https://github.com/Kinge-Service/team3-multibuild.git']]])
			}
		}
		stage('parallel-stage'){
			parallel{
				stage('parallel-job1'){
					steps{
						sh ' sudo systemctl status jenkin'
					}
				}
				stage('parallel-job2'){
					steps{
						echo "welcome to Kinge services"
					}
				}
			}
		}
		stage('second-parallel-stage'){
			when {
				branch ' develop'
			}
			parallel{
				stage('parallel-job3'){
					steps{
						sh 'lscpu'
					}
				}
				stage('end of parallel-job'){
					steps{
						echo " end of jobs"
					}
				}
			}
		}
		stage('final stage'){
			steps{
				sh 'df -h'
				sh 'cat /etc/os-release'
			}
		}
	}
}
