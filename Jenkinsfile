pipeline{
  agent any
  stages{
  	stage('version-control'){
  		steps{
  			checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/Lugards123/second-demo-multybranch.git']]])
  		}
  	}
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'testing'
          }
        }
      }
    }
    stage('codebuild'){
    	steps{
        echo 'thank you elifeTech'
        echo 'the new week is here'
    	}
    }
  }
}
