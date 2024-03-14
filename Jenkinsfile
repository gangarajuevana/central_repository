pipeline {

  agent any
  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          bat "mvn test"
      }
    }

     stage('Deployment') {
      steps {
            bat 'mvn -U -V -e -B -DskipTests -Ptest deploy -DmuleDeploy -Danypoint.platform.client_id="744000e308f94d07b5324ffcdfe13bde" -Danypoint.platform.client_secret="71d38A74c9344C27A2C67607207c6Fa9" -Dusername="gangarajuevana_1437" -Dpassword="Raju@123"'
      }
    }
    
  }
  }
