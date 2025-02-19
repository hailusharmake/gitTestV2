pipeline {
     agent any
         stages {
             stage('Build') {
                 steps {
                     echo 'Application is in Building Phase'
                     bat 'mvn clean install'
                     }
                 }
             stage('Test') {
                 steps {
                     echo 'Application is in Testing Phase'
                     bat 'mvn test'
                       }
                 }
                 stage('Deploy to Cloudhub') { 
                   environment {
                                 ANYPOINT_CREDENTIALS = credentials('anypointplatform')
                               }
                   steps {
                            bat 'mvn deploy -DmuleDeploy -DmuleVersion=4.8.0 -Dusername=sharmakejan20 -Dpassword=Cabaye!3664 -DworkerType=MICRO -Dworkers=1 -Dregion=us-east-1'
                         }
                    }
         }
}
