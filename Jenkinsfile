pipeline{
    agent any
    stages {
        stage("Stage 1") {
	    when {
              buildingTag()
	    }
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
