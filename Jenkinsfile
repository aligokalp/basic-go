pipeline{
    agent { docker 'golang:1.7.3-alpine'}
    stages{
	
	    stage('Clone') {
		   steps{
		          echo "Clone Successfully!"
				  git credentialsId: 'SeckinsGit', url: 'https://github.com/seckins/helloworld-go.git'
		   }
		}
		
		stage('Test') {
		   steps{
				 script {
                 withEnv(["GOPATH=${WORKSPACE}"]) {
				     sh 'go version'
				     sh '$GOPATH/src'
					 sh 'go test'
					 		 
               }
                  }
				  
				  
		          echo "Test passes Successfully!"
		   }
		}
		
		stage('Build') {
		   steps{
		          sh 'docker build -t hw:3.0 . -f Dockerfile'
		          echo "Build passes Successfully!"
		   }
		}
	
	    stage('Deploy') {
		   steps{
					echo 'Passed!'
				}
		}
	}
}