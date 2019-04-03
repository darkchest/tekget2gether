pipeline {
  agent any

  stages {
    stage('Prepare') {
      steps {
        echo "Prepare environment"
      }
    }

    stage('Build') {
      steps {
        //build docker container and push image to ECR
        awsCodeBuild (
          credentialsId: 'codebuild-role',
          credentialsType: 'jenkins',
          projectName: 'demo',
          region: 'us-east-1',
          sourceControlType: 'project',
          sourceVersion: "$GIT_BRANCH",
          envVariables: "[ { ENVIRONMENT, qa }]"
        )
      }
    }

    stage('Deploy to QA') {
      steps {
        sh "Deploy to QA"
      }
    }
  }
}
