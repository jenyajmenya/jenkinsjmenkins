pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/jenyajmenya/jenkinsjmenkins.git'

                // Install nginx.
                sh "apt-get install nginx"
            }
       }
    }
}