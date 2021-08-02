
Skip to content
Pull requests
Issues
Marketplace
Explore
@pratyush-in
pipelineascodecourse /
source_code

4
21

    180

Code
Issues 1
Pull requests 1
Actions
Projects
Wiki
Security

    Insights

source_code/bonus-lectures-jenkins-jobs/withMaven_simple_java_project/withMaven_simple_java_project.txt
pipelineascodecourse example code
Latest commit d92ddb9 on Nov 17, 2018
History
0 contributors
138 lines (111 sloc) 2.98 KB
(withMaven - 1st example)
-------------------------

node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(maven: 'maven3_0_5') {
      sh "mvn clean install"
    }
  }
}

(change of maven version example - 2nd example)
-----------------------------------------------
node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(maven: 'maven3_5_2') {
      sh "mvn clean install"
    }
  }
}

(mavenLocalRepo - 3rd example)
-------------------------------
node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(        
        maven: 'maven3_5_2',
        mavenLocalRepo: '/var/lib/jenkins/local_maven_repo') {

		sh "mvn -X clean install"
    } 
  }
}

(mavenSettingsConfig - 4th example)
------------------------------------
node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(
        maven: 'maven3_5_2',
        mavenSettingsConfig: '') {
            
      sh "mvn -X clean install"

    } 
  }
}

(mavenSettingsFilePath - 5th example)
------------------------------------
node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(
        maven: 'maven3_5_2',
        mavenSettingsFilePath: '/opt/apache-maven-3.0.5/conf/settings.xml') {

      sh "mvn -X clean install"

    } 
  }
}

(all 3 parameters specified - 6th Example)
------------------------------------------
//mavenSettingsConfig takes precedence over mavenSettingsFilePath
node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(
        maven: 'maven3_5_2',
		mavenSettingsFilePath: '/opt/apache-maven-3.0.5/conf/settings.xml',
        mavenSettingsConfig: '',
		mavenLocalRepo: '/var/lib/jenkins/local_maven_repo') {

      sh "mvn -X clean install"

    } 
  }
}

(using jdk)
-----------
node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(maven: 'maven3_5_2', jdk: 'java11') {
      sh "mvn clean install"
    }
  }
}
(using mavenOpts)
-----------------
node{
  stage ('Build') {
	cleanWs()
    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(maven: 'maven3_5_2', jdk: 'java11', mavenOpts: '-XX:+PrintCommandLineFlags -XX:+UseConcMarkSweepGC') {	  
      sh "mvn clean install"
    }
  }
}


(using junitPublisher(disabled: true), artifactsPublisher(disabled: true))
--------------------------------------------------------------------------
node{
  stage ('Build') {

    git url: 'https://github.com/pipelineascodecourse/simple_java_project'

    withMaven(
        options: [junitPublisher(disabled: true), artifactsPublisher(disabled: true)],        
        maven: 'maven3_5_2') {
		
      sh "mvn -X clean install"
    } 
  }
}

    © 2021 GitHub, Inc.
    Terms
    Privacy
    Security
    Status
    Docs

    Contact GitHub
    Pricing
    API
    Training
    Blog
    About

Loading complete
