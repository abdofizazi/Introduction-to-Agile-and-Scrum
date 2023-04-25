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
      when{
        expression{
          BRANCH_NAME == 'dev'
        }
      }
      steps {
        echo 'testing the app..'
        nodejs('node-16'){
          sh 'npm install'
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
