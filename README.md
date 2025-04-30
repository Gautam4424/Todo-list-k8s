# Django To-Do List Application on Kubernetes

Welcome to the **Django To-Do List** application! This repository contains all the Kubernetes configurations required to deploy the Django app on Kubernetes. These configurations include:

- **`namespace.yml`**: Defines the Kubernetes namespace for the Django app.
- **`deploy.yml`**: Deployment configuration for the Django app.
- **`service.yml`**: Defines the Kubernetes service to expose the Django application.

---

## 🚀 Kubernetes Setup Flow

### 1. **Namespace Configuration (`namespace.yml`)**:
The `namespace.yml` file creates the `python-django` namespace within the Kubernetes cluster. This is essential to isolate the Django app’s resources and make it easier to manage.

#### **How to apply**:

kubectl apply -f namespace.yml

This command will create the necessary namespace, ensuring that the resources deployed for the Django application are isolated in the python-django namespace.

2. **Django Deployment (deploy.yml)**:
The deploy.yml file contains deployment settings for the Django app, including replica count, environment variables, and container image for scaling the app in your Kubernetes cluster. This configuration ensures that your application is deployed in an optimal way, with replicas for fault tolerance and scaling.

**How to apply**:

kubectl apply -f deploy.yml -n python-django

This command will create a deployment for the Django app in the python-django namespace. It defines how many instances (replicas) of the Django application to run, environment variables, and other configurations necessary for the application to run properly in the Kubernetes environment.

3. **Service Exposure (service.yml)**:
The service.yml file exposes the Django app within Kubernetes using the notes-app-service. This makes it accessible within the Kubernetes cluster and allows communication with the app from other services or external clients.

**How to apply**:

kubectl apply -f service.yml -n python-django

This command will create the service in the python-django namespace. It will expose the Django app internally within the Kubernetes cluster and make it discoverable via the service name notes-app-service.

🌐 **Accessing the Application**
Once the app is deployed, you can access it using kubectl port-forward. This exposes the service to your local machine for testing and development purposes.

How to forward the port:


kubectl port-forward service/notes-app-service -n python-django 8000:8000 --address=0.0.0.0

After running this command, the Django app will be accessible at http://localhost:8000. The kubectl port-forward command will create a tunnel from your local machine to the service in your Kubernetes cluster, allowing you to interact with the application as if it were running locally.

**🛠 How to Use**
1. Clone the Repository:
Clone this repository to your local machine:


git clone https://github.com/yourusername/yourrepository.git

cd yourrepository

This command will clone the repository to your local machine so you can begin working with the files.

2. **Apply Kubernetes Configurations**:
Apply the configuration files in the following order to set up your application in Kubernetes:


kubectl apply -f namespace.yml
kubectl apply -f deploy.yml -n python-django
kubectl apply -f service.yml -n python-django

These commands will set up the namespace, deployment, and service within your Kubernetes cluster.

3.** Port Forwarding**:
Once the Kubernetes objects have been applied, use the following command to expose the app locally:


kubectl port-forward service/notes-app-service -n python-django 8000:8000 --address=0.0.0.0

This command allows you to forward traffic from your local machine's port 8000 to the service in Kubernetes, allowing you to interact with the Django app on http://localhost:8000.

4. **Visit the Django Application**:
Open your browser and visit http://localhost:8000 to access the To-Do List app!

📂 **Files Description**
**namespace.yml**: Defines the python-django namespace in Kubernetes. This helps organize the resources related to the Django app within a specific namespace.

**deploy.yml**: Contains the deployment configuration for the Django To-Do List application, including replica count, environment variables, and the Docker container image to be used for running the application.

**service.yml** : Defines the Kubernetes service configuration that exposes the Django application to other services or external clients. The service makes it discoverable and accessible within the Kubernetes cluster.

🎉** Conclusion**
With the provided Kubernetes configurations, you can easily deploy and manage the Django-based To-Do List application on Kubernetes. These configurations make it simple to deploy the app, expose it as a service, and access it locally using port forwarding.

Feel free to modify the configurations according to your needs and environment!

📝 **License**
This project is licensed under the MIT License - see the LICENSE file for details.










