pipeline {
    agent {
        node {
            label 'agent1'
        }
    }
    
    tools {
        maven 'maven3.6.0'
    }
    
    stages {
        stage('Build') {
            steps {
                sh '${M2_HOME}/bin/mvn clean package'
            }
        }
        stage('Test') {
            steps {
		sleep 10
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sshagent(credentials : ['13fd51db-e744-4af6-b5d6-1aef2856a26d']) {
                    sh 'scp **/*.war jenkins@10.0.24.43:/opt/tomcat/webapps/'
                }
            }
        }
    }
}
