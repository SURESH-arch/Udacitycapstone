pipeline {
	agent any
	stages {

		stage('Create Kubernetes Cluster') {
			steps {
				withAWS(region:'us-east-1', credentials:'aws-id') {
					sh '''
						eksctl create cluster \
						--name udacitycluster \
						--version 1.14 \
						--nodegroup-name standard-workers \
						--node-type t2.small \
						--nodes 2 \
						--nodes-min 1 \
						--nodes-max 3 \
						--node-ami auto \
						--region us-east-1 \
						--zones us-east-1a \
					'''
				}
			}
		}

		stage('Configure kubectl') {
			steps {
				withAWS(region:'us-east-2', credentials:'aws-id') {
					sh '''
						aws eks --region us-east-2 update-kubeconfig --name udacitycluster
					'''
				}
			}
		}

	}
}
