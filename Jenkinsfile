pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh 'rsync -av -e "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/vismayaServerKey.pem" /var/lib/jenkins/workspace/chatapp_pipeline/ ubuntu@10.0.4.142:/home/ubuntu/new_chatapp'
			}
		}

		stage('Deploy') {
			steps {
				sh 'ssh -i /var/lib/jenkins/vismayaServerKey.pem ubuntu@10.0.4.142 sudo systemctl restart gunicorn'
			}
		}
	}
}
