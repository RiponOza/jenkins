#!/usr/bin/env groovy

def FOLDER_NAME


pipeline{
     
     agent any
     
     environment{
          FOLDER_NAME = "${REPO_NAME}"
     }
        
     stages{
                
        stage('Create folder') {
           steps{
               
                sh """
                    mkdir ${REPO_NAME}
                    cd ${REPO_NAME}
                    touch README
                """
                echo """Folder ${REPO_NAME} is created."""
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
               rm -r ${REPO_NAME}
            """
            echo """Dir ${REPO_NAME} is deleted."""
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
          
          stage('Printing output from script'){
               steps{
                    script{
                         def MSG_OUTPUT = sh(
                              script: "echo 'Value is 67889' "
                         )
                         echo " Output is :===> ${env.MSG_OUTPUT} "
                    }
               }
          }
    }
}     
