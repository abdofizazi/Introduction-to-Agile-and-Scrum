pipeline {
  agent any
  
  stages {
    stage("build") {
      steps {
        script{
          test=1+ 1>2? "Cool": "Not Cool"
          echo test
        }
        echo 'Building the app..'
      }
    }
    stage("test") {
      steps {
        echo 'testing the app..'
        nodejs('node-16'){
          sh 'npm init'
          sh 'npm install  express cors'
        }
      }
    }
    stage("deploy") {
      steps {
        echo 'Deploying the app..'
      }
    }
  }
}
