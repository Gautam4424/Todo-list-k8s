# Django To-Do List Application on Kubernetes

This repository contains the Kubernetes configurations required to deploy the **Django To-Do List** application using Kubernetes. The configurations include:

- **`namespace.yml`**: Defines the Kubernetes namespace for the Django app.
- **`deploy.yml`**: Deployment configuration for the Django app.
- **`service.yml`**: Defines the Kubernetes service to expose the Django application.

---

## Kubernetes Setup Flow

1. **Namespace Configuration (`namespace.yml`)**:
   - The `namespace.yml` file creates the `python-django` namespace.
   
   **How to apply:**
   ```bash
   kubectl apply -f namespace.yml
