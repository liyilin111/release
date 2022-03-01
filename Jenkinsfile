pipeline {
    agent{
        node{
            label 'master'
        }
    }
    tools{
        maven 'maven3'
    }
    options {
        buildDiscarder logRotator(
                        daysToKeepStr: '15',
                        numToKeepStr: '10'
            )
    }
    
    environment {
        APP_NAME = "CWF_APP"
        APP_ENV = "DEV"
    }
    
    stages {
        
        stage('stage 1') {
            steps{
                sh 'echo "Stage 1 Completed - 19035327"'
            }
        }
        parallel {
            stage('stage 2') {
                steps{
                    sh 'echo "Stage 2 Completed - 19035327"'
                }
            }
            
            stage('stage 3') {
                steps{
                    sh 'echo "Stage 3 Completed - 19035327"'
                }
            }
        }
        stage('stage 4') {
            steps{
                def proceedOrAbort = input(message: 'Proceed to release the work?', ok: 'Proceed';
                                        parameters: booleanParam(ok: true)
            }
        }
        
        stage('stage 5'){
            steps{
                sh 'echo "Work Released - 19035327"'
            }
            
        }
    }
}
