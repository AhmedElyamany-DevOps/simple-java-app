pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo 'build in progress'
      }
    }

    stage('Test') {
      steps {
        echo 'test in progress'
      }
    }
  }

  post {
    success {
      slackSend(
        channel: '#jenkins-ci',
        message: "Build Success - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)",
        teamDomain: 'yamoo-workspace',
        tokenCredentialId: 'Slack-notifications'
      )
    }

    failure {
      slackSend(
        channel: '#jenkins-ci',
        message: "Build Failed - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)",
        teamDomain: 'yamoo-workspace',
        tokenCredentialId: 'Slack-notifications'
      )
    }
  }
}
