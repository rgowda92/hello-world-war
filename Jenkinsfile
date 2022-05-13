pipeline{
    agent{ label 'master' }
    stages{
    stage('checkout'){
            steps{
            sh "rm -rf hello-world-war"
            sh "git clone https://github.com/rgowda92/hello-world-war.git"
            }
            }
    stage('build'){
    steps{
    sh "pwd"
    sh "ls"
    sh "sudo chmod 666 /var/run/docker.sock"   
    sh "docker build -t tom:1.0 ."
    }
    }
    stage('publish'){
           steps{
              sh"docker login-u rakesh412 -p rakeshmp@07"
              sh "docker pull rakesh412/dockerimage:1.0"
           }  
       }    
       stage('deploy'){
           agent{ label 'slave' }
           steps{
              sh "docker login -u rakesh412 -p rakeshmp@07"
              sh "docker pull rakesh412/docker image:1.0"
              sh "docker run -d -p 8050:8080 --name trial rakesh412/dockimage:1.0"
            }     
        }  
      }        
    }
