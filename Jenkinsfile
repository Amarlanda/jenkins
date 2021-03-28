properties([pipelineTriggers([githubPush()])])
pipeline {
  /* specify nodes for executing */
  agent {
    label 'github-ci'
  }

  stages {
    /* checkout repo */
    stage('Checkout SCM') {
      steps {
        checkout([
          $class: 'GitSCM',
          branches: [[name: 'master']],
          userRemoteConfigs: [[
            url: 'git@github.com:wshihadeh/rabbitmq_client.git',
            credentialsId: '',
            ]]
          ])
        }
      }

    stage('Preparation') {
      steps {
        sh 'ls'
        git 'https://github.com/Amarlanda/jenkins.git'
        sh 'echo hello'
        sh 'echo hello'
        }
    }

    stage ('checkout'){
      steps {
        sh 'mvn test'
      }
      
    }
  }
}
