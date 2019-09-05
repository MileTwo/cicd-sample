pipeline {
  agent {
    label "myjenkins-jenkins-slave"
  }
  environment {
    ORG = 'mile-two'
    APP_NAME = 'm2demo'
  }
  stages {

    // stage("Dependency Check") {
    //   steps {
    //     dependencyCheck () 
    //     //dependencyCheckPublisher pattern: ''
    //     //archiveArtifacts allowEmptyArchive: true, artifacts: '**/dependency-check-report.*', onlyIfSuccessful: true

    //   }
    // }


    stage('Build Release') {
      when {
        branch 'cicd'
      }
      steps {
        container('nodejs') {
          sh "npm install"
          sh "npm run build"
        }
      }
    }
  }
}
