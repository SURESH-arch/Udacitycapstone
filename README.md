Udacity Cloud DevOps Capstone Project.
Project Overview
Blue /green deployment 
1)	Created infrastructure using cloud formation scripts
aws cloudformation create-stack --stack-name capstinfra  --template-body file://jenkins-server.yml  --parameters file://jenkins-server-parameters.json
{
    "StackId": "arn:aws:cloudformation:us-east-2:821556368364:stack/capstinfra/14c7fb30-33f0-11eb-a1af-0ac225ff6c98"
}
2)	Jenkins was setup – Plugins Blue-ocean and Aws-pipeline installed
3)	Added AWS credentials in Jenkins
4)	Connected to GitHub https://github.com/SURESH-arch/udacitycapstone.git

5)	 Created EKS cluster
     Configured kubectl using CI/CD pipeline
6)	Created Docker credentials 
7)	In the final step build the pipeline for docker push and Service Pointing to Blue Replication Controller is build and after approval green pod will run 
and final step is completed.
