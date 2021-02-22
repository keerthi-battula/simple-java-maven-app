pipeline {
agent any
    tools{
        maven 'maven'
        jdk 'jdk'
    }
stages {
stage ('bulid')
{
steps {
sh 'mvn -B -DskipTests clean package'
}
}
stage ('test')
{
steps 
{
sh 'mvn test'
}

}
}
}
