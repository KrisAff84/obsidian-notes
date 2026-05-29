# Querying

### Describe Logs Resource Policies

```shell
aws logs describe-resource-policies | jq '.resourcePolicies[].policyDocument | fromjson'
```

### Get Resources By Tag

```shell
# This will show all other tags associated with the resource
aws resourcegroupstaggingapi get-resources \
    --tag-filters Key=<tag_key>,Values=<tag_value>
   
# This will show the resource ID only
aws resourcegroupstaggingapi get-resources \
    --tag-filters Key=<tag_key>,Values=<tag_value> | grep ResourceARN
```

### See What Resource is Using a Specific Security Group

```shell
aws ec2 describe-network-interfaces \
  --filters Name=group-id,Values=<sg-id> \
  --query 'NetworkInterfaces[*].{ID:NetworkInterfaceId,Type:InterfaceType,Description:Description,InstanceId:Attachment.InstanceId}' \
  --output table
```

### See What Resource is Using a Specific ENI

```shell
aws ec2 describe-network-interfaces \
  --network-interface-ids eni-x000000000000000 \
  --query 'NetworkInterfaces[*].{ID:NetworkInterfaceId,Type:InterfaceType,Description:Description,InstanceId:Attachment.InstanceId}' \
  --output table
```