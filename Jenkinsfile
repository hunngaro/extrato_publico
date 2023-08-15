
node (label: 'build && linux') {
  stage('Clean Workspace'){
    cleanWs()
  }

  stage("Main build") {
    docker.image('node:8').pull()

    stage('Checkout SCM') {
    }
    
    // Permorming Install and Lint
    docker.image('node:8').inside {
      stage('Install') {
        sh label:
          'Running npm install',
        script: '''
          node --version
          cd extrato-publico
          npm install
        '''
      }

    }

    stage ('Build') {
      docker.image('node:8').inside {
        sh label:
          'Running npm run build',
        script: '''
          node --version
          cd extrato-publico
          npm run build
        '''
      }
    }
  }


}
