pipeline {
  agent any

  stages {

    stage('compile code') {
        steps {
        sh '''
            mvn compile
        '''
        }
    }

    stage('clean package') {
        steps {
        sh '''
            mvn package
        '''
        }
    }
    stage('Prepare Artifacts') {
       steps {
       sh '''
         zip -r ../users.zip *
       '''
       }
    }

  }
}
