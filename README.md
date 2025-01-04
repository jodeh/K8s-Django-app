<h1>Django Demo on K8s</h1>
<br>
<h3>Description</h3>
<hr>
<p>Simple webapp demo on minikube using django with mysql as database & nginx ingress</p>
<hr>
<h3>usage</h3>
1. start minikube
```
minikube start --driver docker
```
2. Clone the repository
```
git clone https://github.com/jodeh/K8s-Django-app.git
cd K8s-Django-app
```
3. Enable ingress addon
```
minikube addons enable ingress
```
4. Add Node ip to hosts file
```
echo "$(minikube ip) jodeh.xyz" | sudo tee -a /etc/hosts
```
5. Create the namespaces
```
kubectl create namespace development
kubectl create namespace database
```
6. Deploy application
```
kubectl apply -f .
```
