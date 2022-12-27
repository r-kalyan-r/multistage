pipeline{
    agent any
    stages {
        stage("main branch script ") {
            when {
                branch "main"
		    // Build only when main branch  
            }
            steps {
	             script {
                       def pom = readMavenPom file: 'pom.xml'
                       env.version = pom.version
                       echo "main branch version is ${env.version}"
                }
            }
        }
        stage("develop branch script"){
            when {
                branch "develop"
              // scan all the folders and check if there is change in python script       
            }
            steps {
	                      script {
                       def pom = readMavenPom file: 'pom.xml'
                       env.version = pom.version
                       echo "develop branch version is ${env.version}"
                }

		 }          
        }
	stage("bug-fix branch script"){
            when {
                branch "bug-fix"
              // scan all the folders and check if there is change in python script
            }
            steps {
                              script {
                       def pom = readMavenPom file: 'pom.xml'
                       env.version = pom.version
                       echo "develop branch version is ${env.version}"
                }

                 }
        }

	stage("feature branch script"){
            when {
                branch "feature-*"
  // builds on when branch starts with feature-  
            }
            steps {
	           script {
                       def pom = readMavenPom file: 'pom.xml'
                       env.version = pom.version
                       echo "Feature branch version is ${env.version}"
                 }
        }
    }
}
}
