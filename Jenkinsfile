pipeline{
     agent any
        
     stages{
                
        stage('Create folder') {
           steps{
                sh '''
                cd /root/
                mkdir dkjj2jh3432h4k32h4kj
                cd dkjj2jh3432h4k32h4kj
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
            cd /root/
            rm -r dkjj2jh3432h4k32h4kj
            '''
            echo 'Dir dkjj2jh3432h4k32h4kj is deleted.'
            echo 'Good Bye!'
           }
        }
    }
}     
