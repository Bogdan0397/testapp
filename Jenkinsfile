pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'docker build -t myapp .'
      }
    }

    stage('Test') {
      steps {
        sh '''
          pip install -r requirements.txt
          pytest
        '''
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker-compose up -d'
      }
    }
  }
}
