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
bat 'mvn -B -DskipTests clean package'
}
}
stage ('test')
{
steps 
{
bat 'mvn test'
}

}
}
}
