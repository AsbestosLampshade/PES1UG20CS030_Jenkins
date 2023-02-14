pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
        sh 'mvn test'
        echo 'Tested Successfully'
        post{
          always{
            junit 'target/surefire-reports/*.xml'
          }
        }
      }
    }
    stage('Deploy'){
      steps{
        sh 'mvn deploy'
        echo 'Deployed Successfully'
      }
    }
  }
  post{
    failure{
      echo 'Pipeline failed' 
    }
  }
}
