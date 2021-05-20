pipeline {
  agent {
    label 'NODEJS'
  }
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
         cp target/*.jar users.jar
         zip -r users.jar users.zip
       '''
       }
    }
  }
}
