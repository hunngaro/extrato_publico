
node (label: 'build && linux') {
  stage('Clean Workspace'){
    cleanWs()
  }

  stage("Main build") {
     
    // Permorming Install and Lint
    docker.image('node:10').inside {
      stage('Install') {
        sh label:
          'Running npm install',
        script: '''
          node --version
          cd hello-world-node
          npm install
        '''
      }

    }

      }
    stage ('Build') {
      docker.image('node:10').inside {
        sh label:
          'Running npm run build',
        script: '''
          node --version
          cd hello-world-node
          npm run build
        '''
      }
    }
  }


