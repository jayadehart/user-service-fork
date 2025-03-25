Here is how to run the infrastructure for this project.

To initialize the IAM roles neccessary to run the github actions, run this code from your command line:

```
aws cloudformation deploy \
  --stack-name github-actions-cloudformation-deploy-setup \
  --template-file cloudformation-templates/setup.yml \
  --capabilities CAPABILITY_NAMED_IAM \
  --region <region> \
  --parameter-overrides GitHubOrg=<your org or account name> RepositoryName=<your repository name>
```

This will run the code found in setup.yml.

Once that is done, you can re-run the jobs in github and it should deploy the necessary infrastructure and ECS tasks.
