pipeline{
   agent any
   stages{
     stage('checkout'){
       steps{
      	sh'git pull https://github.com/manojugowda/hello-world-war.git'
	}
      }
	   stage('build'){
        steps{
	sh 'mvn clean package'
    }
   }
	   	   stage('root'){
        steps{
	sh 'sudo su -'
    }
   }
	   	   stage('copy'){
        steps{
	sh 'cp /home/ubuntu/hello-world-war/target/hello-world-war-1.0.0.war /opt/apache-tomcat-9.0.56/webapps/'
    }
   }
  }
 }
