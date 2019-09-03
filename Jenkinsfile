pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
   stage('Init') {
	steps {
	 sh 'rm -rf nodejs_app'
	 git branch: 'master',
	 url: 'https://github.com/wl-devops-074/repo.git'
      }
    }

    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
     
    
  }
}
