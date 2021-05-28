pipeline {
  agent any

  stages {

    stage('Lint Check') {
      steps {
        sh '''
          jslint '**/*.js' || true
        '''
      }
    }

    stage('Prepare Artifacts') {
      steps {
        sh '''
          mkdir -p publish 
          cp -r static publish
        '''
      }
    }

    stage('Publish Artifacts') {
      steps {
        sh '''
          cd publish
az artifacts universal publish --organization https://dev.azure.com/srimaanaws2021/ --feed srimaanaws2021 --name rsfrontend --version 1.0.6 --description "Welcome to Universal Packages" --path .
        '''
      }
    }

  }

}