pipeline {
    agent any
    stages {
        stage("sonar quality check") {
            steps {
                echo "Run pipeline sonar quality check"
                echo "OK"
            }
        }
        stage("docker build") {
            echo "Docker build"
            steps {
                script {
                    app = docker.build("thiennguyen98/devops_lab_java_gradle_responsive_website")
                }
            }
        }
        stage("docker push") {
            echo "Docker push"
            steps {
                script {
                    docker.withRegistry("https://registry.hub.docker.com", "docker-thiennguyen") {
                        app.push("${env.BUILD_NUMBER}")
                        app.push("lastest")
                    }
                }
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