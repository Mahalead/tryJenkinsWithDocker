pipeline {
    agent {
        node {
            label "docker-agent-jdk17"
        }
    }
    triggers {
      pollSCM 'H/6 * * * *'
    }
    stages {
        stage("Build") {
            steps{
                echo "Building"
                sh '''
                cd myApp
                pip install -r requirements.txt
                '''
            }
        }
        stage("Test") {
            steps{
                echo "Testing"
                sh '''
                cd myApp
                python3 hello.py
                python3 hello.py --name=Dominic
                '''
            }
        }
        stage("Deliver") {
            steps{
                echo "Delivering"
                sh '''
                echo "doing delivery stuff..."
                sleep 50
                '''
            }
        }
    }
}
