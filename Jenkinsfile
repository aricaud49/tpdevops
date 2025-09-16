pipeline {
    agent { label 'Agent_AME' }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'luksor',
                    url: 'https://github.com/aricaud49/tpdevops.git'
            }
        }
		stage('Build') {
            steps {
			  script {
               def customImage = docker.build("aricaud49/tp_devops:v1")

                /* Push the container to the custom Registry */
                customImage.push()
			  }
            }
        }
	}		
}
