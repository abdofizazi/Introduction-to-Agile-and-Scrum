pipeline {
  agent any
  environment{
    NEW_VERSION = "1.20.11"
    DB_CREDENTIALS = credentials("db-server")
  }
  stages {
    stage("build") {
      steps {
        script{
          test=1+ 1>2? "Cool": "Not Cool"
          echo test
        }
        echo "Building the app with version ${NEW_VERSION}"
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
        echo DB_CREDENTIALS
      }
    }
  }
  post{
    always{
      echo "Built done"
    }
    success{
      echo "Built with success.."
    }
    failure{
      echo "Failed"
    }
  }
}
