pipeline {
  agent any

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
  }
}	
