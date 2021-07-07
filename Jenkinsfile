node {
  stage ('Build') {
    checkout scm
    withMaven (maven: 'maven'){
      sh "mvn clean verify"
    } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
  }
}
