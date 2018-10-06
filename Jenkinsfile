pipeline {
    agent {
        docker {
            image 'maven:3.5.4-jdk-8'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
        }
        stage('Build') { 
            steps {
                sh 'mvn package' 
            }
        }
        stage('Publish') {
            steps {
                nexusPublisher nexusInstanceId: 'localNexus', nexusRepositoryId: 'maven-releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: '/var/lib/jenkins/workspace/petclinic/target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar']], mavenCoordinate: [artifactId: 'petclinic-jar', groupId: 'petclinic', packaging: 'foo', version: '2l0']]]
            }
        }
    }
}
