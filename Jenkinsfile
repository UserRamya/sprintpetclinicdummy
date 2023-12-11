pipeline {
    
    agent any

    options {             
         timeout(time: 30, unit: 'MINUTES')
    }
   
    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('git') {
            steps {                
                git url: 'https://github.com/UserRamya/sprintpetclinicdummy.git'
                    branch: 'dev2'
            } 
            
        }
    

        stage('build') {
            steps {
                sh 'mvn clean package'
                   archiveArtifacts artifacts: '**/spring-petclinic-*jar'
            }
        }
    }

}