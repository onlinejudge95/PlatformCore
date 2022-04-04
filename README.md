PlatformCore
============

## Setup
1. Before installing the helm chart make sure the secrets section defined below are installed
2. Install custom charts using the `charts` dir

### K8s-Dashboard
1. Add k8s-dashboard helm repo
```bash
$ helm repo add kubernetes-dashboard https://kubernetes.github.io/dashboard/
```
2. Install the dashboard
```bash
$ helm install k8s-dashboard kubernetes-dashboard/kubernetes-dashboard
```
3. Get the security token for login
```bash
$ kubectl --namespace kube-system describe secret deployment-controller-token-<UUID>
```
4. Set up kubernetes proxy
```bash
$ kubectl proxy
```
5. Access the dashboard from localhost using this URI `http://localhost:8001/api/v1/namespaces/default/services/https:k8s-dashboard-kubernetes-dashboard:https/proxy/#/login`

## Secrets
1. `kubectl create secret generic --from-env-file=./charts/postgres/.env postgres-secret`

## TODOs
1. Fix tests in `postgres`
1. Fix tests in `redis`
