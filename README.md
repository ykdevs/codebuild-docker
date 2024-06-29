# codebuild-docker

## Install


環境変数設定

```shell
STACK_NAME=CodeBuildDocker
TEMPLATE=codebuild.yaml
```

パラメータ設定

```shell
PARAMETERS='[ { "ParameterKey": "BranchName", "ParameterValue": "main" } ]'
```

実行

```shell
aws cloudformation create-stack --stack-name ${STACK_NAME} \
  --template-body file://./cloudformation-templates/${TEMPLATE} \
  --parameters "${PARAMETERS}" \
  --capabilities CAPABILITY_NAMED_IAM
```

更新

```shell
aws cloudformation update-stack --stack-name ${STACK_NAME} \
  --template-body file://./cloudformation-templates/${TEMPLATE} \
  --parameters "${PARAMETERS}" \
  --capabilities CAPABILITY_NAMED_IAM
```


削除

```shell
aws cloudformation delete-stack --stack-name ${STACK_NAME}
```