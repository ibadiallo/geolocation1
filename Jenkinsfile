pipeline {
    agent any
    tools{
  maven 'M2_HOME'      
    }
    triggers {
  pollSCM('* * * * *')
    }
    stages {
        stage('maven build') {
            steps {
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
                sleep 5
            }
        }
          stage('Test') {
            steps {
                sh 'mvn test'
                
            }
        }
          stage('Deploy') {
            steps {
                echo 'echo deploy Step'
                sleep 10
            }
        }
          stage('Docker') {
            steps {
                echo 'Image step'
                sleep 4
            }
        }
    }
}
