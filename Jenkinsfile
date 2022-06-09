pipeline{
	agent any
	stages{
		stage ('git version-control'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-oz', url: 'https://github.com/racheldev-code/jenkins-parallel-job1.git']]])
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
