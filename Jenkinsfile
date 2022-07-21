pipeline {

  agent any

  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean  -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          bat "mvn test"
      }
    }

     stage('Deployment') {
   
      steps {
            bat 'mvn -U -V -e -B -DskipTests deploy -Dapp.runtime=4.4.0 -Denvironment=Sandbox -Dcloudhub.application.name=jenkins-deploy-two -Dregion=us-east-2 -Dworkers=1 -DworkerType=MICRO -DmuleDeploy'
      }
    }

  }
}
