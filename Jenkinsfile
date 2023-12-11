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
            step {                
                git url: 'https://github.com/UserRamya/sprintpetclinicdummy.git'

                   branch: 'dev2'
                   
            } 
            
        }
    

        stage('build') {
            step {
                sh 'mvn clean package'
                archiveArtifacts artifacts: '**/spring-petclinic-*jar'
            }
        }
    }

}