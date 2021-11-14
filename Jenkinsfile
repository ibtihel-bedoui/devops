pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[
                            credentialsId: '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',
                            url: 'https://github.com/ibtihel-bedoui/devops.git']]])
                }
            }
        }
	stage('Install') {
             steps{
                script{
                    sh "sudo npm install"
                }
            }
        }

	stage ('Build') {
	
			steps {
			
			sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
	
			}


	}


}}
