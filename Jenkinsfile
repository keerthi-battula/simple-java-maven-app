pipeline {
agent any
    tools{
        maven 'maven'
        jdk 'JDK11'
    }
stages {
stage("build & SonarQube analysis") {
            
            steps {
              withSonarQubeEnv('sonar-server') {
                bat 'java -version'
                bat 'mvn clean package sonar:sonar'
              }
            }
          }
    stage('collect artifact'){
     steps{
     archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
     }
     }
     stage('deploy to artifactory')
     {
     steps{
     
     rtUpload (
    serverId: 'Artifactory-Server',
    spec: '''{
          "files": [
            {
              "pattern": "target/*.jar",
              "target": "art-doc-dev-loc"
            }
         ]
    }''',
 
  
    buildName: 'holyFrog',
    buildNumber: '42'
)
     }}
}
}
