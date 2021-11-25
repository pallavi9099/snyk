node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/pallavi9099/snyk.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '72ae82be-129a-4317-a738-d10d0a4ae92a', snykInstallation: 'Snyknew', snykTokenId: 'Snykkey'
       
   }

}
