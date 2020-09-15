# ecs-fargate-example

### Deploy CodePipeline:


set -e

aws-vault exec "profile-name" --no-session -- sam package --s3-bucket "bucket-name"
aws-vault exec "profile-name" --no-session -- sam deploy --s3-bucket "bucket-name" --stack-name "stack-name" \
   --capabilities CAPABILITY_IAM 