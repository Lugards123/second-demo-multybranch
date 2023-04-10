pipeline{
  agent any
  stages{
  	stage('version-control'){
  		steps{
  			checkout scmGit(branches: [[name: '*/main'], [name: '*/(mainldevlfeature)']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/Lugards123/second-demo-multybranch.git']])
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
            echo 'action2'
          }
        }
        stage('sub-job3'){
            steps{
                echo 'action3'
            }
        }
      }
    }
    stage('codebuild'){
    	steps{
    		sh 'cat /etc/passwd'
    	}
    }
  }
}
