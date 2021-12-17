pipeline {
  agent any
  
    stages {
    
         stage('Get Latest'){
            steps {
            sh 'git pull origin master'
            echo "latest code updated"
            }
        }
      
         stage('Install dependencies'){
            steps {
            sh 'mvn clean package'
            echo "Modules installed"
            }
         }
  
        stage('Sending Email'){
          steps {
            //emailext attachLog: true, body: 'Check Build Report', subject: 'Build Report', to: 'beingaliabid@gmail.com'
            emailext attachLog: true, body: 'Check Build Report', postsendScript: '$DEFAULT_POSTSEND_SCRIPT', presendScript: '$DEFAULT_PRESEND_SCRIPT', replyTo: '$DEFAULT_REPLYTO', subject: 'Build Report', to: 'beingaliabid@gmail.com'
            }
        }
      
           }

      
         }
