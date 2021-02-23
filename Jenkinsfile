pipeline {
agent any
    tools{
        maven 'maven'
        jdk 'JDK11'
    }
stages {
stage ('bulid')
{
steps {
bat 'mvn -B -DskipTests clean package'
}
}
stage("build & SonarQube analysis") {
            
            steps {
              withSonarQubeEnv('sonar-server') {
                bat 'java -version'
                bat 'mvn clean package sonar:sonar'
              }
            }
          }
}
}
