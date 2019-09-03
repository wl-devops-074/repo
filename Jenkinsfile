pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
   stage('Init') {
	steps {
	 sh 'rm -rf nodejs_app'
	 git branch: 'pr-10',
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
     
    stage('publish package to npmjs') {
      steps {
        sh'npm config set registry https://registry.npmjs.com/'
        sh 'npm publish --access=public'
       }
    }
  }
}
