pipeline {
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
    }
}
