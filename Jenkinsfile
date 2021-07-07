pipeline {
  agent any
  stages {
    stage('Assessment') {
      steps {
        echo 'Analyze build details sent from Wiser Workflow'
        fileExists 'README.md'
      }
    }

  }
}