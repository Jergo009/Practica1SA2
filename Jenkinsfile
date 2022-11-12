pipeline {
  agent any
  tools {nodejs "node"}
  stages {

    stage('Git') {
      steps {
        git branch: 'main', url: 'https://github.com/Jergo009/Practica1SA2'
      }
    }

    stage('Install') {
      steps { sh 'npm install' }
    }

    stage('Test') {
       steps { sh 'npm run test --watch=false' }
    }

    stage('Build') {
      steps { sh 'npm run ng build --configuration="production" --optimization --build-optimizer' }
    }

    stage('Deploy'){
      steps { sh 'mv dist/practica1/* /home' }
    }
  }
}
