pipeline {
    agent { node { label 'Agent-1' } }

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
            }
        }
    }
    post { 
        always { 
            echo 'I will always run whether job is success or not'
        }
        success {
            echo 'I will run only when job is success'
        }
        failure { 
             echo 'I will run when job is failed'
        }
    }
}
