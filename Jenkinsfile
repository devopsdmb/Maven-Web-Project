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
	stage('deploy') {
	
			  
				sh  'cp $WORKSPACE/target/*.war /opt/apache-tomcat-9.0.12/webapps'
}
}
