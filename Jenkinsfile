pipeline {
  agent any

  stages {

    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Deploy to Nginx') {
      steps {
        sh '''
          sudo rm -rf /var/www/html/*
          sudo cp -r * /var/www/html/
          sudo systemctl reload nginx
        '''
      }
    }
  }

  post {
    success {
      echo 'Auto deploy success 🚀'
    }
    failure {
      echo 'Auto deploy failed 💀'
    }
  }
}
