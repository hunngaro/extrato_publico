pipeline {
   agent {
        docker { image 'node:18' }
    }

  stages{
  // stage('Init'){
  //  steps{
  //    sh '''#!/bin/bash
  //    echo "JAVA_HOME = ${JAVA_HOME}";
  //    echo "PATH = ${PATH}";
  //    echo "MAVEN_HOME = ${M2_HOME}";
     
  //    npm install -g @angular/cli@7.3.8;
  //    npm install
  //   '''
    
 
  //   //readFileStep();
  //   println "Init success..";
  //   }
  //  }
      
  // stage('Build'){
  //  steps{
    
  //   echo "Starting build ...."
  //   sh '''#!/bin/bash
  //         ng build --aot --prod
  //    '''
  //   println "BUILD NUMBER = $BUILD_NUMBER"
  //   println "Build Success.."
  //   println " Release Notes: $env.Release_Notes"
  //  }
   
  // }

  stage('Release Notes'){
         stage('Test') {
            steps {
                sh 'node --version'
            }
        }
  }
}
}
