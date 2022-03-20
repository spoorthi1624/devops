pipeline {
    agent any
    options { timestamps () }
  // stages and rest of pipeline.
      triggers {
        cron('* * * * *')
    }
    environment {
        def BUILDVERSION = sh(script: "echo  `date +%y%m%d`'$currentBuild.number'", returnStdout: true).trim()
    }

    stages {
        stage("Awesome Stage") {
            steps {
                echo "Current build version :: $BUILDVERSION"
            }
        }
        stage("git clone") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/spoorthi1624/devops.git'
            }
        }
    }
}
