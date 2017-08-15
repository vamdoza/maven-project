pipeline {
  agent any
  stages {
    stage('Pull') {
      steps {
        git(url: 'https://github.com/vamdoza/maven-project.git', branch: 'master', poll: true)
        echo 'Hello From Pull'
      }
    }
    stage('Compile') {
      steps {
        echo 'Hello From Compilation'
      }
    }
    stage('Test') {
      steps {
        echo 'Hello from running Tests'
      }
    }
  }
}