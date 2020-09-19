# ecs-fargate-example

## About:

Repository contains a aws infrastructure example using cloudformation.
I use aws codepipeline+github for ci/cd. Infrasctruture as compose by fargate+ecs for run a microservice aplication using container.

### Create s3 bucket:

aws s3api create-bucket --bucket my-bucket --region us-east-1

### Deploy CodePipeline:

set -e

aws-vault exec "profile-name" --no-session -- sam package --s3-bucket "bucket-name"

aws-vault exec "profile-name" --no-session -- sam deploy --s3-bucket "bucket-name" --stack-name "stack-name" --capabilities CAPABILITY_IAM 
