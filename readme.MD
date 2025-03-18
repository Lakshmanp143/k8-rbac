
REGION_CODE=us-east-1
CLUSTER_NAME=expense
ACC_ID=503561459301

### IAM permissions
* OIDC privider  #authentication service
```
eksctl utils associate-iam-oidc-provider \
    --region $REGION_CODE \
    --cluster $CLUSTER_NAME \
    --approve
```