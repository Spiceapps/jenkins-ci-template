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

    stage('build') {
      steps {
        bat '''cd src\\MyWindowsService  
        nuget restore -source "https://api.nuget.org/v3/index.json"'''
      }
    }

    stage('deploy service') {
      steps {
        bat 'msbuild src\\\\MyWindowsService\\\\MyWIndowsService\\\\Deploy-Windows-Service-Via-MSBuild.proj'
      }
    }

  }
}