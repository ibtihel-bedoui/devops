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
stage('Docker') {
		steps{
			script {


			sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml "


}
}
}

}}
