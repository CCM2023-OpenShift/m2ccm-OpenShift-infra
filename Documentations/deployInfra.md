# Deploy database
```shell
oc create -f postgresql-deployment.yaml -n lmagniez03-dev
```
# Test database
```shell
oc exec -it $(oc get pods -l app=postgresql -o jsonpath='{.items[0].metadata.name}') -- psql -U admin -d mydatabase
```
```sql
SELECT version();
```
# Get logs
```shell
oc describe deployment postgresql-deployment -n lmagniez03-dev
```
# Delete database
```shell
oc delete -f postgresql-deployment.yaml -n lmagniez03-dev
```