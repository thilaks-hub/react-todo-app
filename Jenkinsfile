pipeline {
    agent any

    tools {

            nodejs('v16.20')
    }    
  
       stages {
           stage('Git  checkout') {
            steps {
                git branch: 'main',url: 'https://github.com/thilaks-hub/react-todo-app.git'
         
            }
        }
    
        stage('Install Packages') {
            steps {
                sh "npm install"
         
            }
        }

        stage('Build code') {
            steps {
                sh 'npm run build'
            }

        }

        stage('Copy  Files') {
            steps {
                     sh 'cp -r build/* /var/www/html'
            }
        }


        stage('Archive Artifacts') {
            steps {
                     sh 'zip -r Thilaks-React-${BUILD_NUMBER}.zip build/'
                     archiveArtifacts artifacts: "Thilaks-React-${BUILD_NUMBER}.zip"
            }
        }

   
    }
}
 
