pipeline {
  agent {
    docker {
      image 'classes-image:latest'
    }
  }

  stages {
    stage('SCM') {
        steps {
      		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/shab-a88/dotnet-console.git']]])
	      }
    }

    stage('Build') {
          steps {
               sh 'dotnet build "$WORKSPACE/classes.csproj"'
          }
    }
  }
}
