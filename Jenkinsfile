pipeline{
	agent any
	
	stages{
		stage ('Compile Stage') {
			steps{
				withMaven(maven : 'maven-3.6.3') {
					bat '''
						echo "PATH = ${PATH}"
						mvn clean compile
					'''
				}
			}
		}
		
		
		stage ('Testing Stage') {
			steps{
				withMaven(maven : 'maven-3.6.3'){
					bat 'mvn test'
				}
			}
		}
		stage ('Deployment Stage') {
			steps{
				withMaven(maven : 'maven-3.6.3'){
					bat 'mvn deploy'
				}
			}
		}
		
	}
}
