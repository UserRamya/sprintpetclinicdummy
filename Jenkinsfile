pipeline {
agent any
stages {
    stage('Build with unit testing') {
        steps {
            bat 'mvn clean package'
        }
    }
}
}