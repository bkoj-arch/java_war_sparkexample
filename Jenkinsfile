pipeline {
  agent any
  stages {
    stage('test windows') {
      parallel {
        stage('test windows') {
          steps {
            sh 'echo "test"'
          }
        }

        stage('test linux') {
          steps {
            sh 'echo test linux'
          }
        }

      }
    }

    stage('verifs') {
      steps {
        fileExists 'pom.xml'
        sh 'ls -la'
      }
    }

    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('publish reports') {
      steps {
        echo 'publish'
      }
    }

    stage('deploy') {
      steps {
        sh 'echo deploy'
      }
    }

  }
}