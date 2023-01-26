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
        
	sh ' [ -e pom.xml ] && echo "le fichier pom.xml existe "'
	sh 'ls -la'
      }
    }

    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }


    stage('deploy') {
      steps {
      deploy adapters: [tomcat9(credentialsId: 'manager_tomcat', path: '', url: 'http://localhost:8080')], contextPath: '/spark', war: 'target/*.war'
    }
}
  }
}
