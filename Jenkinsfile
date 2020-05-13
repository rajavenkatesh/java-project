pipeline {
  agent none

  environment {
    MAJOR_VERSION = 1
  }

  parameters {
    string(name: 'devBuild', defaultValue: 'none', description: 'Build number for the upstream dev build.')
  }

  stages {
    stage('Say Hello') {
      agent any

      steps {
        sayHello 'Awesome Student!'
      }
    }
    stage('Unit Tests') {
      agent any
      
      steps {
        bat 'ant -f test.xml -v'
        junit 'reports/result.xml'
      }
    }
    stage('build') {
      agent any
	  
      steps {
        bat 'ant -f build.xml -v'
      }
      post {
        success {
          archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
        }
      }
    }
  }
  }
