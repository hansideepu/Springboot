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
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
  }
}
