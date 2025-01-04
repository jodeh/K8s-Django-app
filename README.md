# Django Demo on Kubernetes
## **Description**
A simple web application demo deployed on Minikube using:
- **Django**: Web application framework.
- **MySQL**: As the database.
- **NGINX Ingress**: To manage external access to the application.

---

## **Usage**

### 1. **Start Minikube**
Start Minikube with the Docker driver:
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
7. Check jodeh.xyz
