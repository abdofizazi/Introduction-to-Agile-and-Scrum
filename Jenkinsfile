pipeline {
  agent any
  
  stages {
    stage("build") {
      steps {
        script{
          test=1+ 1>2? "Cool": "Not Cool"
        }
        echo 'Building the app..'
      }
    }
    stage("test") {
      steps {
        echo 'testing the app..'
      }
    }
    stage("deploy") {
      steps {
        echo 'Deploying the app..'
      }
    }
  }
}
