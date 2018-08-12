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