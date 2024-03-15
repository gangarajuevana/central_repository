pipeline {

  agent any
  environment {
    //adding a comment for the commit test
    ANYPOINT_CREDS = credentials('anypoint-credentials')
  }

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
       environment {
    //adding a comment for the commit test
    CLIENTID_CREDS = credentials('Client-Id-Test')
    CLIENTSECRET_CREDS = credentials('Client-Secret-test')
  }
      steps {
            bat 'mvn -U -V -e -B -DskipTests -Ptest deploy -DmuleDeploy -Danypoint.platform.client_id="744000e308f94d07b5324ffcdfe13bde" -Danypoint.platform.client_secret="71d38A74c9344C27A2C67607207c6Fa9" -Draju.clientid="%CLIENTID_CREDS%" -Draju.clientsecret="%CLIENTSECRET_CREDS%" -Dusername="%ANYPOINT_CREDS_USR%" -Dpassword="%ANYPOINT_CREDS_PSW%"'
      }
       
    }
    
  }
  }
