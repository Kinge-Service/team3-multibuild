pipeline {
	agent any 
	stages{
			when {
				branch 'main'
			}
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
				echo "success"
			}
		}
	}
}
