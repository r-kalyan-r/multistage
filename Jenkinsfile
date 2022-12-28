pipeline{
    agent any
    parameters {
              gitParameter defaultValue: 'origin/main', name: 'SBRANCH', type: 'PT_BRANCH_TAG',quickFilterEnabled:true ,description: 'Select Branch'
	      }
    stage('Checkout') {
          steps {
            checkout scm: [$class: 'GitSCM', userRemoteConfigs: [[url: 'https://github.com/r-kalyan-r/multistage.git',credentialsId: 'git-token']], branches: [[name: '${SBRANCH}']]], poll: false
          }
        }
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
