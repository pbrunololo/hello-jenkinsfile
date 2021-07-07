 node {
  stage ('Build') {
    checkout scm
    withMaven (maven: 'maven'){
      sh "mvn clean package"
    } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
  }
    stage('dependencyTrackPublisher') {
        	dependencyCheckPublisher pattern: 'target/dependency-check-report.xml'
	}
    }
