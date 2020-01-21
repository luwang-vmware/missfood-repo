Steps
1. kubectl create ns app-ns
2. kubectl create serviceaccount app -n app-ns
3. kubectl apply -f psp.yaml
4. kubectl apply -f cluster_role.yaml
5. kubectl apply -f cluster_role_binding.yaml
or kubectl create clusterrolebinding app:app-ns:app-cluster-role --clusterrole=app-cluster-role --serviceaccount=app-ns:app
6. kubectl create test-pod --image ubuntu --serviceaccount app -n app-ns
