pipeline {
    agent any

    options {
       timeout(time: 10, unit: 'HOURS') 
    }

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('git') {
            steps {
                // Use single quotes for the URL and add parentheses for the git step
                script {
                    git(url: 'https://github.com/UserRamya/sprintpetclinicdummy.git', branch: 'dev2')
                }
            }
        }

        stage('build') {
            steps {
                // Use double quotes for the shell command
                //sh "mvn clean package"
                
                // Archive the JAR file with a more specific path
               // archiveArtifacts artifacts: '**/*.jar'
               junit testresults: '**/TEST*.xml'
            }
        }
    }

    post {
        success {
            echo 'Build and package successful!'
        }
        failure {
            echo 'Build or package failed!'
        }
    }
}
