```
cd eks
terraform init -upgrade
terraform plan -var-file="dev.tfvars"
terraform apply -auto-approve -var-file="dev.tfvars"
```
