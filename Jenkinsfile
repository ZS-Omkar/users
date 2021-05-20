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
         zip -r ../users.zip *
       '''
       }
    }
    stage('Upload Artifacts') {
        steps {
            sh '''
            curl -v -u admin:Omkar@123 --upload-file /home/ubuntu/workspace/users.zip http://172.31.4.7:8081/repository/users/users.zip
            '''
        }
    }
  }
}
