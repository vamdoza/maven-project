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
        parallel(
          "Test": {
            echo 'Hello from running Tests'
            
          },
          "Mac Test": {
            echo 'Mac Test'
            
          },
          "Windows Test": {
            echo 'logging to the screen'
            sh 'date > log.txt'
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        writeFile(file: 'result.txt', text: 'the result of the deploy', encoding: 'utf-8')
      }
    }
  }
}