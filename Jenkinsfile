pipeline {
  agent any
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/masonaarons/whaling_jenkins.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t masonaarons/whaling_example'
      }
    }

    stage('Login') {
      steps {
        sh 'docker login -u masonaarons dckr_pat_ahsibeib'
      }
    }

    stage('Push') {
      steps {
        sh 'docker push -u masonaarons/whaling-jenkins'
      }
    }

  }
}