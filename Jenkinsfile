 node {
  stage ('Build') {
    checkout scm
    withMaven (maven: 'maven'){
      sh "mvn clean package"
    } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
  }
  stage('dependencyCheckPublisher') {
    {  
     withMaven(maven : 'maven') {  
      sh 'mvn dependency-check:check'  
     }  
   
     dependencyCheckPublisher pattern: 'target/dependency-check-report.xml'  
   }  
  }
}
