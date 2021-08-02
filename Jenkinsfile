node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(maven: 'maven3_0_5') {
      sh "mvn clean install"
    }
  }
}

