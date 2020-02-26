# spinnaker-kustomize

The project is part of our internal ci/cd process leveraging how we are managing spinnaker. 
This allows to use halyard in free flow way using kustomize. 

Pre-requisite,
Setup spinnaker managing and managed iam using the guide, you only need to add aws account if you want to enable lambda.
https://docs.armory.io/spinnaker-install-admin-guides/add-aws-account/
Cross account IAM are required for ecr since ecr catalogue api are not exposed to iam role/user of another account.

Currently supported and production tested functionalities:
1. Using IRSA (service account based iam for eks, we use this for cross account setup as well).
2. Using Taint and tolerations to allow to run whole spinnaker on 1 big node.
3. Using elasticache redis
4. Ecr cross-account autodiscovery, needs spinnaker roles in managed account. Read more here (https://docs.armory.io/install-guide/adding_accounts/)
5. Aws lambda support. Read more here (https://kb.armory.io/aws/AWS-Lambda-HowTo/)
6. Included a spinnaker pipeline to update spinnaker itself.
