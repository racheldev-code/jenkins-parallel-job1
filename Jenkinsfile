pipeline{
	agent any
	stages{
		stage ('git version-control'){
			steps{
				git checkout
			}
		}
		stages('parallel-job'){
			parallel{
				stage('sub-job1'){
					steps{
						echo 'action1'
					}
				}
				stage('sub-job2'){
					steps{
						echo 'action2'
					}
				}
			}
		}
		stage('codebuild'){
			steps{
				sh 'cat /etc/passwd'
			}
		}
	}
}