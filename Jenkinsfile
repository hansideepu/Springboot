pipeline {
    agent any
      stages {
         // def mvnHome= tool "Maven"
         stage ('Build') {
            steps {
                //sh '${mvnHome}/bin/mvn/ clean install -f pom.xml'
              bat 'mvn -Dmaven.test.failure.ignore=true clean package' 
            }
        }
    }
}
