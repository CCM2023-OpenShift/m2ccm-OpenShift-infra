# Deploy database
```shell
oc create -f ./infrastructure/postgresql-deployment.yaml -n lmagniez03-dev
```
# Test database
```shell
oc exec -it $(oc get pods -l app=postgresql -o jsonpath='{.items[0].metadata.name}') -- psql -U admin -d mydatabase
```
```sql
SELECT version();
```
# Delete database
```shell
oc delete -f ./infrastructure/postgresql-deployment.yaml -n lmagniez03-dev
```