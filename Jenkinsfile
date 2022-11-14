#!/usr/bin/env groovy

def FOLDER_NAME


pipeline{
     
     agent any
     
     environment{
          FOLDER_NAME = "${params.REPO_NAME}"
     }
        
     stages{
                
        stage('Create folder') {
           steps{
                sh """
                    mkdir "${FOLDER_NAME}"
                    cd "${FOLDER_NAME}"
                    touch README
                """
                echo """Folder ${FOLDER_NAME} is created."""
                echo "README is created."
                }
        }
        stage('Wait for 30 sec'){
            steps{
                echo 'Enter into sleep mode !'
                sh'''
                sleep 30
                '''
                echo 'Exiting sleep mode !'
                }
        }
        stage('Deleting created folder'){
          steps{  
            sh"""
               rm -r ${FOLDER_NAME}
            """
            echo """Dir ${FOLDER_NAME} is deleted."""
            echo 'Good Bye!'
           }
        }
          stage('Running python file'){
               steps{
                 sh '''
                    chmod 777 hello_world.py
                    python hello_world.py
                 '''
               }
          }
    }
}     
