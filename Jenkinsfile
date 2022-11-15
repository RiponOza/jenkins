#!/usr/bin/env groovy

//changes are made

def FOLDER_NAME
def MSG_OUTPUT
def PYTHON_FILE


pipeline{
     
     agent any
     
     environment{
          FOLDER_NAME = "${REPO_NAME}"
          PYTHON_FILE = "hello_world.py"
          
     }
     
     parameters{
          booleanParam(defaultValue:false, description:"Set flag variable as True/False", name: "FLAG")
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
          
          
        stage('Wait for 5 sec'){
            steps{
                echo 'Enter into sleep mode !'
                sh'''
                sleep 5
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
      
          
          stage('Running python file with command line args'){
               steps{
                 sh """
                    chmod 777 hello_world.py
                    python ${env.PYTHON_FILE} ${FIRST_NAME} ${LAST_NAME}
                 """
               }
          }
          
          
          stage('Printing output from script'){
               steps{
                    script{
                         MSG_OUTPUT = sh(
                              script: "echo 'Value is 67889' ",
                              returnStdout: true
                         )
                         echo " Output is :===> ${MSG_OUTPUT} "
                    }
               }
          }
          
          
          stage('Running groovy if-else'){
               steps{
                    script{
                              if(params.FLAG == true){
                                   echo "FLAG variable has true value."
                                   return
                              }
                              else{
                                   echo "FLAG variable has false value."
                              }
                         }
                     }
          }
          
      
          stage('Printing environment variables'){
               steps{
                    echo """ FOLDER_NAME = ${env.FOLDER_NAME} """
               }
          }
    }
}     
