pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'touch /home/amar'
            }
        }
    }
}
 
