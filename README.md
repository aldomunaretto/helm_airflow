

https://marclamberti.com/blog/airflow-on-kubernetes-get-started-in-10-mins/


https://github.com/helm/charts
https://github.com/airflow-helm/charts/blob/main/charts/airflow/values.yaml


helm repo add apache-airflow https://airflow.apache.org
helm repo update
helm search repo airflow
helm install airflow apache-airflow/airflow --namespace airflow --debug


helm show values apache-airflow/airflow > values.yaml

helm ls -n airflow

helm upgrade --install airflow apache-airflow/airflow -n airflow -f values.yaml --debug 

kubectl create secret generic airflow-ssh-git-secret --from-file=gitSshKey=/Your/path/.ssh/id_rsa -n airflow
kubectl get secrets -n airflow

python3 -c 'import secrets; print(secrets.token_hex(16))'