pipeline {
 agent any

tools { 
    
        git 'localGit'
        jdk 'localJava'
        nodejs 'localNode'
}
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
   }
   post {  
          always {
            -----------Post build steps ------
    
           }
    
       }
   
  }
}
}
