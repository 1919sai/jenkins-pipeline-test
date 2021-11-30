pipeline{
 agent any{
	stages{
	
			stage('Build Application'){
			steps{
			bat 'mvn clean install'
				}
			}
			stage('Deploy Application to CloudHub'){
			steps{
			bat 'mvn clean package deploy -Dusername=16DCs191 -Dpassword=16DCs191 -DapplicationName=Auto-Gitcode-Jenkins-Deployment -Denvironment=Sandbox -Dworkers=1 -DworkerType=Micro -DobjectStoreV2=true -DmuleDeploy'
				}
			}
			stage('Perform Regression Testing'){
			steps{
			bat 'newman run E:\\newman_testing\\hello-world.postman_collection.json --disable-unicode'
				}
			}
		}
	}
 }
