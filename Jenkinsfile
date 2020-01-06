pipeline {
	agent none
	stages { 
	
	stage('Non-Parallel Stage') {
		agent {
				label "master"
				
				} 
		steps {
				echo " This stage will be executed first"
				} 
		}
		
		stage('Run Tests') { 
		
			parallel {
				stage('Test on slave1') {
					agent {
							label "slave1"
					}
					steps {
							echo "Task1 on Agent"
							sh label: '', script: 'sudo touch text2333322.txt'
					}
				
				}	
				stage('Test on slave2') {
					agent { 
							label "slave2"
					} 
					steps {
							echo "Task2 on Agent"
							sh label: '', script: 'sudo touch text333333221.txt'
					}
					
				}			
			}
		}			
		
	}
}	
