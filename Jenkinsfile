//pipeline {
  //  agent any
    //  stages {
      //    def mvnHome= tool 'Maven'
        //  withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
          //   stage ('Build') {
            //    steps {
              //      bat '${mvnHome}/bin/mvn/ clean install -f pom.xml'
          //        //bat 'mvn -Dmaven.test.failure.ignore=true clean package' 
        //        }
      //      }
    //    }
  //  }
//}
pipeline {
  agent any
  tools {
    maven 'Maven'
    jdk 'Java11'
  }
  stages {
    stage('Build') {
      steps {
        bat 'mvn -Dmaven.test.failure.ignore=true clean package' 
      }
    }
    stage ('Deploy') {
            steps{
              deploy adapters: [tomcat9(credentialsId: '3c921852-8b67-4f6f-bf6d-b6c033b64661', path: '', url: 'http://localhost:8090/')], contextPath: '\' \'', war: '**/*.war'
              echo "Deploy successful";
            }
        }
    }
}
