pipeline
{
	agent any
	stages
	{
		stage('Initialize')
		{
			steps
				{
					echo "Initialize stage"
					  echo "PATH = ${PATH}"
                   			 echo "M2_HOME = ${M2_HOME}"
				}
		}
		
		stage('Build')
		{
			steps
				{
					sh 'mvn clean package'
				}
				post
				{
					success
					{
						echo 'Now Archiving'
						archiveArtifacts artifacts : '**/*.war'
					}
				}
		}
		
		stage('Deploy')
		{
			steps
				{
					echo "Deploy stage"
				}
		}
		
	}
}
