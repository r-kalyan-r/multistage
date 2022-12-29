pipeline{
    agent any
    environments {
       ENV = "Prod"
    }
    stages {
        stage("Stage 1") {
	  when {
            environment(name: "ENV", value: "Prod")
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
	   when {
            environment(name: "ENV", value: "Dev")
	   }
            steps {
	              script {
                       def pom = readMavenPom file: 'pom.xml'
                       env.version = pom.version
                       echo "develop branch version is ${env.version}"
                }

	    }          
        }
	stage("Stage 3"){
	   when {
              environment(name: "system", value: "QA")
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
