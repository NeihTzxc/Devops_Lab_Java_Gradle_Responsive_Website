pipeline {
    agent any
    stages {
        stage("sonar quality check") {
            steps {
                echo "Run pipeline sonar quality check"
                echo "OK"
            }
        }
        stage("docker build and docker push") {
            steps {
                echo "Running pipeline docker build and push"
            }
        }
        stage("Pushing the helm charts to nexus") {
            steps {
                echo "Running pipeline pushing the helm chars to nexus"
            }
        }
        stage("Manual Approval") {
            steps {
                echo "Running pipeline manual approval"
            }
        }
    }
}