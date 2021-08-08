pipeline {
    agent any
    
    environment {
        PROJECT_NAME = "Pipelane"
        OWNER_NAME = "Mykhailo Kolodii"
    }

    stages {
        stage('Build-1') {
            steps {
                echo 'Hello World'
                echo "Building......"
                echo "End of Stage Build"
                sh   "pwd"
            }
        }
        stage('Test-2') {
            steps {
                echo "Start of Stage Test"
                echo "Testing............"
                sh   "ls -la"
                echo "End of Stage Build"
                echo "Hello ${OWNER_NAME}"
                echo "Project name is ${PROJECT_NAME}"
            }
        }
        stage('Deploy-3') {
            steps {
                echo "Start of stage deploy"
                echo "Deploying.........."
                sh '''
                   echo "Line-1"
                   echo "Line-2"
                '''
                echo "End of Stage Build"
            }
        }
    }
}
