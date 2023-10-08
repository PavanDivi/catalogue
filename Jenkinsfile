pipeline {
    agent { node { label 'Agent-1' } }
    
    options {
        ansiColor('xterm')
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Unit Testing is Done here..'
            }
        }
        
        // stage('sonar scan') {
        //     steps {
        //         sh 'ls -ltr'
        //         sh 'sonar-scanner'
        //     }
        //}
        stage('Build') {
            steps {
                sh 'ls -ltr'
                sh 'zip -r ./* --exclude=.git --exclude=.zip'
            }
        }
        stage('Publish Artifacts') {
            steps {
               nexusArtifactUploader(
nexusVersion: 'nexus3',
protocol: 'http',
nexusUrl: '44.202.26.153:8081/',
groupId: 'com.roboshop',
version: '1.0.0',
repository: 'catalogue',
credentialsId: 'nexus-auth',
artifacts: [
[artifactId: 'catalogue',
classifier: '',
file: 'catalogue.zip',
type: 'zip']
]
)   
            }
        }
    }

}
