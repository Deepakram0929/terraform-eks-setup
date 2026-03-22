```
Step1:
aws configure
cd eks
terraform init -upgrade
terraform plan -var-file="dev.tfvars"
terraform apply -auto-approve -var-file="dev.tfvars"
```
```
step2:

aws dynamodb create-table \
  --table-name Lock-Files \
  --attribute-definitions AttributeName=LockID,AttributeType=S \
  --key-schema AttributeName=LockID,KeyType=HASH \
  --billing-mode PAY_PER_REQUEST \
  --region us-east-1

aws dynamodb list-tables --region us-east-1
terraform init -reconfigure

```

```
step3:

To access the private cluster 
1.lunch ec2 instance --> attach public VPC of cluster
2.iam roles --> ssm AmazonSSMManagedInstanceCore
3.install kubectl , awscli
4.aws configure
5.aws eks update-kubeconfig --region us-east-1 --name uat-eks-cluster

```
