# aws-login
A Kubernetes cronJob to access the Amazon ECR Registries. 

## Git Clone
```git
git clone https://github.com/iramarJunior/aws-kubectl.git
```

## Create a Secret

```bash
AWS_ACCOUNT=
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=
AWS_REGION=

kubectl create secret generic aws-secret \
    --from-literal=AWS_ACCOUNT=$AWS_ACCOUNT \
    --from-literal=AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID \
    --from-literal=AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY \
    --from-literal=AWS_DEFAULT_REGION=$AWS_DEFAULT_REGION \
    --from-literal=AWS_REGION=$AWS_REGION
```

### or

```bash
# modify src/aws-secret.yaml
kubectl apply -f templates/aws-secret.yaml
```

## Create cronJob
```bash
kubectl apply -f templates/aws-registry-credential-cronjob.yaml
# trigger the first run
``` 
