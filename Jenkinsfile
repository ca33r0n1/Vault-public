pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git(changelog: true, url: 'https://github.com/Iskallia/Vault-public.git', branch: 'master')
      }
    }

    stage('Build') {
      steps {
        sh 'gradlew clean build'
      }
    }

    stage('Pull Jar\'s') {
      steps {
        archiveArtifacts(fingerprint: true, artifacts: '*.jar')
      }
    }

  }
}