pipeline {
    agent any

    stages {
        stage ('Clone and Compile'){
            steps {
	    sh "print env"
            sh "mvn clean compile"
                
            }
        } 
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'mvn package'
            }
        }
       stage('Archive'){
           steps {
           echo 'Archiving ...'
	   archiveArtifacts '**/target/*.jar'	
             }
       }

    }
}
