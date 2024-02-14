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
        sh 'docker build -t masonaarons/whaling_jenkins'
      }
    }

    stage('Login') {
      steps {
        sh 'docker login -u masonaarons dckr_pat__WvV141tJAlk6Cwss11np8ohEBM'
      }
    }

    stage('Push') {
      steps {
        sh 'docker push masonaarons/whaling-jenkins'
      }
    }

  }
}