#!groovy

node {
	   
	stage('Checkout'){

          checkout scm
       }

       stage('BuildArtifact'){
	       def mvn_version = 'M2_HOME'
	       withEnv( ["PATH+MAVEN=(tool mvn_version)/bin"] )
	       {

          sh 'mvn install'
	       }
       }
	   
      stage('Sonar') {
                    //add stage sonar
	      def mvn_version = 'M2_HOME'
	       withEnv( ["PATH+MAVEN=(tool mvn_version)/bin"] )
	      {
                    sh 'mvn sonar:sonar'
	      }
                }
       
}
