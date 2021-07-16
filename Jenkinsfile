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
              deploy adapters: [tomcat9(credentialsId: '93fc75be-3137-47e0-9113-2b7953f1b6db', path: '', url: 'http://localhost:8090/')], contextPath: 'jenkinsdeploy', war: '**/*.war'
              echo "Deploy successful";
            }
        }
    }
}
