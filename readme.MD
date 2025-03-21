
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
### Service account
```
eksctl create iamserviceaccount \
--cluster=expense \
--namespace=expense \
--name=expense-mysql-secret \
--attach-policy-arn=arn:aws:iam::503561459301:policy/ExpenseMysqlScretRead \
--override-existing-serviceaccounts \
--region us-east-1 \
--approve
```     