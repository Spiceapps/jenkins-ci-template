pipeline {
  agent {
    node {
      label 'windows'
    }

  }
  stages {
    stage('checkout code') {
      steps {
        git(url: 'git@github.com:Spiceapps/jenkins-ci-template.git', branch: 'master', credentialsId: 'jenkins_spiceapps', poll: true)
      }
    }

  }
}