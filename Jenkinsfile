pipeline {
 agent any

 tools {nodejs "nodejs"}

 stages{
  stage('Init'){
   steps{
     sh '''#!/bin/bash
     echo "JAVA_HOME = ${JAVA_HOME}";
     echo "PATH = ${PATH}";
     echo "MAVEN_HOME = ${M2_HOME}";
     
     npm install -g @angular/cli@7.3.8;
     npm install
    '''
    
 
    //readFileStep();
    println "Init success..";
    }
   }
      
  stage('Build'){
   steps{
    
    echo "Starting build ...."
    sh '''#!/bin/bash
          ng build --aot --prod
     '''
    println "BUILD NUMBER = $BUILD_NUMBER"
    println "Build Success.."
    println " Release Notes: $env.Release_Notes"
   }
   
  }

  stage('Release Notes'){
    steps{
      sudo docker run -p 3000:3000 -e REQUEST_METHOD='POST' -e  VERSION="$VERSION" -e ANCERSTORS="4015227154" -e DESCRIPTION="$DESCRIPTION" -e FEATURES="$FEATURES" -e BUGS="$BUGS" -e PROBLEMS="$PROBLEMS" -e PULL_REQUEST="$PULL_REQUEST" release-notes
    }
  }
}
}
