pipeline{
     
     parameters{
          string(name:'folder_name', defaultValue:'default-folder', description:'This is the name of the folder that will be created.')
     }
     
     agent any
        
     stages{
                
        stage('Create folder') {
           steps{
                sh '''
                mkdir ${params.folder_name}
                cd ${params.folder_name}
                touch README
                '''
                echo 'Folder dkjj2jh3432h4k32h4kj is created.'
                echo 'README is created.'
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
            sh'''
            rm -r dkjj2jh3432h4k32h4kj
            '''
            echo 'Dir dkjj2jh3432h4k32h4kj is deleted.'
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
