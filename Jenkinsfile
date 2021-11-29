pipeline {

     agent any

         stages {

             stage(‘Build’) {

                 steps {

                     echo ‘Application is in Building Phase’

                     bat ‘mvn clean install’

                     }

                 }

             stage(‘Test’) {

                 steps {

                     echo ‘Application is in Testing Phase’

                     bat ‘mvn test’

                       }

                 }

                 stage(‘Deploy to Cloudhub’) { 

                   environment {

                                 ANYPOINT_CREDENTIALS = credentials(‘platform.credentials’)

                               }

                   steps { 

bat ‘mvn clean package deploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -DapplicationName=DemoJenkinsApplication -Denvironment=Sandbox -Dworkers=1 -DworkerType=Micro -DobjectStoreV2=true -DmuleDeploy’

                         }

                    }

         }

     }