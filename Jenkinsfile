node {
  stage ('Build') {
    checkout scm
    withMaven (maven: 'maven'){
      sh "mvn clean package"
    } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
  }
    stage('dependencyTrackPublisher') {
            withCredentials([string(credentialsId: 'api_key_dependency', variable: 'API_KEY')]) {
                dependencyTrackPublisher artifact: 'target/bom.xml', projectName: 'my-project', projectVersion: 'my-version', synchronous: true, dependencyTrackApiKey: API_KEY
        }
    }
}
