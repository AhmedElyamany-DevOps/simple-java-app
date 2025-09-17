pipeline{

  agent any

  stages{
    stage('build'){
      steps{
        script{
          echo "build in progress"
        }
      }
    }

  stage('test'){
     steps{
       script{
          echo "test in progress"
        }
      }
    }
  }
}

post {
  success {
    slackSend channel: '#jenkins-ci', message: slackSend "Build Success - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'yamoo-workspace', tokenCredentialId: 'Slack-notifications'
  }
  failure {
    slackSend channel: '#jenkins-ci', message: slackSend "Build Failed - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'yamoo-workspace', tokenCredentialId: 'Slack-notifications'
  }
}


