## AWS

```
# configure multiple profiles
$ aws configure --profile account1
$ aws configure --profile account2

$ ~/.aws/credentials

[profileName1]
aws_access_key_id=***************
aws_secret_access_key=***************

[profileName2]
aws_access_key_id=***************
aws_secret_access_key=***************

$ serverless deploy --aws-profile <profilename>

```

### example using serverless.yml
https://www.serverless.com/framework/docs/providers/aws/guide/credentials/
```
service: new-service
provider:
  name: aws
  runtime: nodejs12.x
  stage: ${opt:stage, self:custom.defaultStage}
  profile: ${self:custom.profiles.${opt:stage, self:provider.stage, 'dev'}}
custom:
  defaultStage: dev
  profiles:
    dev: devProfile
    prod: prodProfile
```
