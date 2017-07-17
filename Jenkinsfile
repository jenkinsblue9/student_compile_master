pipeline {
  agent any
  stages {
    stage('clone') {
      steps {
        git(url: 'https://github.com/carreerit/mavenrepo.git', branch: 'master', poll: true)
      }
    }
    stage('Maven') {
      steps {
        parallel(
          "Maven": {
            sh 'mvn clean '
            
          },
          "st1": {
            sh 'mvn compile'
            
          },
          "st2": {
            sh 'mvn package'
            
          }
        )
      }
    }
  }
}