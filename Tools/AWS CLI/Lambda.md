# Lambda

### Invoke Lambda and Get Response in Terminal

```shell
aws lambda invoke \
    --cli-binary-format raw-in-base64-out \
    --function-name <function_name> \
    --payload '{"Key1": "Value1"}' \
    /dev/stdout | jq '.'
```
