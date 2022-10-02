pipeline {
   agent any
   
//environment {

      //sonar_url = 'http://18.224.57.72:9000/'
      //sonar_username = 'admin'
      //sonar_password = 'admin'
//}  
 
   stages {
   	stage('checkout') {
         steps {
            // Get some code from a GitHub repositoryn
            git 'https://github.com/wakaleo/jenkins-the-definitive-guide-book.git'
        }
       
        }
    stage ('Compile and Build') {
         steps {
           sh '''
	   cat pom.xml
	   mvn clean install -U  -Dmaven.test.skip=true
           '''
         }
}
       }

	   post {
        always {
              emailtext body: 'build success is ${BUILD_NUMBER}', subject:'Build success', to:'ramyaupputuri99@gmail.com'
            }
           }        
}
