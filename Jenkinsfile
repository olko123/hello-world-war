node {
   def mvnHome
   stage('Preparation') { // for display purposes
      mvnHome = tool 'maven3.6.0'
   }
   stage('Build') {
      // Run the maven build
      sh "'${mvnHome}/bin/mvn' clean package"
   }
}
