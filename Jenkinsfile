pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/dummy.txt'
                sh 'echo "body" > build/dummy.txt'
                sh 'echo "head" >> build/dummy.txt'
                sh 'echo "engine" >> build/dummy.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'test -f build/dummy.txt'
                sh 'grep "body" build/dummy.txt'
                sh 'grep "head" build/dummy.txt'
                sh 'grep "engine" build/dummy.txt'
            }
        }
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
