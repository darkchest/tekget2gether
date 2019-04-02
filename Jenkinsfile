pipeline {
  agent any

  stages {
    stage('Prepare') {
      steps {
        echo "Prepare environment"
      }
    }

    stage('Deploy to QA') {
      steps {
        sh "ecs-deploy --help"
      }
    }
  }
}
