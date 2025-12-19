pipeline {
  agent any

  stages {

    stage('Checkout Code') {
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
      echo 'Deploy success 🎉'
    }
    failure {
      echo 'Deploy failed 💀'
    }
  }
}
