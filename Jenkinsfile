pipeline {
    agent any

  stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your version control system
               script {
                    git(url: 'https://github.com/UserRamya/sprintpetclinicdummy.git', branch: 'dev3')
                }
            }
        }

      

    post {
        success {
            echo 'Build and tests passed!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}