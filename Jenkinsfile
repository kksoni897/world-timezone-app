pipeline
	{
		agent any
		stages
			{
				stage("Build Application")
					{
						steps
							{
							bat 'mvn clean install -DskipTests'
							}
					
					}
					
				stage("Munit Testing")
					{
						steps
							{
							bat 'mvn test'
							}
					
					}
					
				stage("Deploy Application to CloudHub")
					{
						steps
						{
							bat 'mvn package deploy -DmuleDeploy -DskipTests'
						}
					}
					
				stage("Perform Regression Testing")
					{
						steps
						{
							bat 'C:\\Users\\gs-2193\\AppData\\Roaming\\npm\\newman run C:\\KrishnaSoni_WorkSpace\\Project_Mule\\postmanCollection\\world-timezone.postman_collection.json --disable-unicode'					
							bat 'C:\\Users\\gs-2193\\AppData\\Roaming\\npm\\newman run C:\\KrishnaSoni_WorkSpace\\Project_Mule\\postmanCollection\\world-timezone.postman_collection.json --disable-unicode -r htmlextra --reporter-htmlextra-export C:\\KrishnaSoni_WorkSpace\\Project_Mule\\postmanCollection'
						}
					}
			}
	}
