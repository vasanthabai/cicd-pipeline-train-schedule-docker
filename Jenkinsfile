pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
  stage('Build Docker Image') {
when {
branch 'master'
}
steps {
script { 
    app = docker.build("[dockerhub username]/train-schedule")
    }
}
