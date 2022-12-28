pipeline{
    agent any
    parameters {
              gitParameter defaultValue: 'origin/main', name: 'SBRANCH', type: 'PT_BRANCH_TAG',quickFilterEnabled:true ,description: 'Select Branch'
	      }
    stages {
        stage("Stage 1") {
            steps {
	             script {
                       def pom = readMavenPom file: 'pom.xml'
                       env.version = pom.version
                       echo "main branch version is ${env.version}"
                }
            }
        }
        stage("Stage 2"){
            steps {
	              script {
                       def pom = readMavenPom file: 'pom.xml'
                       env.version = pom.version
                       echo "develop branch version is ${env.version}"
                }

	    }          
        }
	stage("Stage 3"){
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
