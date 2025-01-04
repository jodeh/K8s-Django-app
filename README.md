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
### 2. **Clone the Repository**
Clone the GitHub repository and navigate to the project directory:
```
git clone https://github.com/jodeh/K8s-Django-app.git
cd K8s-Django-app
```
### 3. **Enable the Ingress Addon**
Enable the ingress addon in Minikube:
```
minikube addons enable ingress
```
### 4. **Update /etc/hosts File**
Add the Minikube node's IP to the hosts file to associate the application domain:
```
echo "$(minikube ip) jodeh.xyz" | sudo tee -a /etc/hosts
```
### 5. **Create the namespaces**
```
kubectl create namespace development
kubectl create namespace database
```
### 6. **Deploy application**
Apply all Kubernetes configurations from the current directory:
```
kubectl apply -f .
```
### 7. **Access the Application**
Visit the application at http://jodeh.xyz in your browser.
