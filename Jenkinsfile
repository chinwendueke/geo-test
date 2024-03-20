pipeline{
    agent any 
    tools{
        maven 'M2_HOME'
    }
    stages {
    stage('maven clean'){
        steps{
            sh 'mvn clean '
        }
    }
    stage('maven install'){
        steps{
            sh 'mvn install'
        }
    }
    stage('maven package'){
        steps{
            sh 'mvn package'
        }
    }
    stage('upload artifact'){
        steps{
            sh 'curl --upload-file target/bioMedical-0.0.1-SNAPSHOT.jar -u admin/devops -v http://ec2-34-204-95-60.compute-1.amazonaws.com:8081/#admin/repository/repositories:maven-nexus-repo'
        }
    }    
    }

}
