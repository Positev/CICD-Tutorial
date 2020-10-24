pipeline {
    agent {
        docker {
            image 'node' 
            args '-p 10083:3000' 
        }
    }
    stages {
        stage('CI') { 
            steps {
                sh 'yarn --cwd ./App/ticker' 
                sh 'CI=true yarn --cwd ./App/ticker test' 
                sh 'yarn --cwd ./App/ticker run build --if-present' 
            }
        }

    }
}
