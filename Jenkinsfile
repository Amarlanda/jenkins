node {
  stage('Preparation') {
    poll scm// for display purposes
    sh 'ls'
    git 'https://github.com/Amarlanda/jenkins.git'
    sh 'echo hello'
  }
  stage ('checkout'){
    sh 'mvn test'
  }
}
