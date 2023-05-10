pipeline {
  agent any
  stages {
    stage('Log Tool Version') {
      parallel {
        stage('Log Tool Version') {
          steps {
            sh '''mvn --version
                  git --version
                  java -version'''
          }
        }

      }
    }

    stage('Build') {
      agent {
        docker {
          image 'alpine'
        }

      }
      steps {
        sh 'echo "this is a build step for a sample docker image alpine"'
        dockerNode(image: 'alpine')
      }
    }

    stage('Test') {
      steps {
        sh 'echo "test the job"'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "Deploy to prod env"'
      }
    }

  }
}