pipeline {
    agent any
    tools {
        maven 'Maven 3'
        jdk 'jdk8'
    }
    stages {
         stage ('Build') {
            steps {
              bat "mvn -version"
              bat "mvn clean install"
            }
        }
    }
}
