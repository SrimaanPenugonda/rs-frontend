pipeline {
  agent any

  stage {

    stage('Prepare Artifacts') {
      steps {
        sh '''
          mkdir publish 
          cp -r static publish
        '''
      }
    }

    stage('Publish Artifacts') {
      steps {
        sh '''
          cd publish
          az artifacts universal publish --organization https://dev.azure.com/DevOps-Batches/ --project="DevOps53" --scope project --feed devops53 --name frontend --version 0.0.21 --description "Welcome to Universal Packages" --path .
        '''
      }
    }

  }

}