
# Tilt Demo Project

## Overview

### What is Tilt and Why Do We Need It?

Tilt is a powerful tool designed to simplify and streamline the development of microservices, especially in Kubernetes environments. It enables developers to efficiently manage, build, and deploy their applications by providing real-time feedback and automatically rebuilding and redeploying code changes. With Tilt, you can see how your application behaves in a production-like environment during development, making it easier to detect and fix issues before they reach production.

In essence, Tilt acts as a bridge between your development environment and Kubernetes, allowing for faster iteration and more effective testing. By using Tilt, you can focus on writing code rather than managing complex deployment pipelines.

### About This Project

This project is a simple demonstration of how to use Tilt to build, deploy, and test a Python Flask application in a Kubernetes environment. The application is a basic Flask server that responds with a simple message. The project demonstrates how to configure Tilt to automatically watch for changes, rebuild the Docker image, and redeploy the application in Kubernetes, providing an efficient development workflow.

## Project Structure

The project structure is organized as follows:

```
TiltDemo/
├── Tiltfile
├── app/
│   ├── Dockerfile
│   ├── app.py
│   └── requirements.txt
└── kubernetes/
    └── deployment.yaml
```

- **Tiltfile**: The configuration file that Tilt uses to build the Docker image and deploy the Kubernetes resources.
- **app/**: Contains the Flask application source code and the Dockerfile for building the Docker image.
  - **Dockerfile**: Defines how the Docker image is built.
  - **app.py**: The main Flask application code.
  - **requirements.txt**: Specifies the Python dependencies for the Flask application.
- **kubernetes/**: Contains the Kubernetes deployment configuration.
  - **deployment.yaml**: Defines the Kubernetes Deployment for running the Flask application.

## Instructions

### Prerequisites

Before you start, ensure you have the following tools installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Kubernetes](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [Tilt](https://docs.tilt.dev/install.html)

### Steps to Run the Project

1. **Clone the Repository**

   Clone the repository to your local machine:

   ```bash
   git clone https://github.com/Talh12/TiltDemo.git
   cd TiltDemo
   ```

2. **Update Dependencies**

   Ensure the correct versions of the dependencies are set in `requirements.txt`:

   ```plaintext
   Flask==2.0.3
   Werkzeug==2.0.3
   ```

3. **Start Tilt**

   Run Tilt in the root of your project:

   ```bash
   tilt up
   ```

   This command will:
   - Build the Docker image for the Flask application.
   - Deploy the application to your Kubernetes cluster.
   - Automatically watch for changes and redeploy as needed.

   You can monitor the status of your application via the Tilt dashboard, which will be available in your web browser.

4. **Access the Application**

   Once the application is running, you can access it at:

   ```
   http://localhost:5000
   ```

### Modifying the Project

To modify the project, simply edit the files in the `app/` or `kubernetes/` directories. Tilt will automatically detect the changes, rebuild the Docker image, and redeploy the application.

#### Example

1. Open the `app.py` file in the `app/` directory.
2. Find the following line of code:
   ```python
   return "Hello, Tilt!"
   ```
3. Replace "Hello, Tilt!" with your name or any text you like, such as:

```python
return "Hello, [Your Name]!"
```
4. Save the file.

Tilt will automatically rebuild the Docker image and redeploy the application. Once this is done, refresh http://localhost:5000 in your browser to see your changes take effect.
This should work perfectly with your project setup. When you make the change in `app.py` and refresh the browser, you should see the updated message, showcasing how Tilt handles live updates. If you follow these steps, you should see Tilt automatically rebuild and redeploy your app with the updated message.


## Conclusion

This project demonstrates the power of Tilt in simplifying the development workflow for Kubernetes-based applications. By using Tilt, you can significantly reduce the complexity of managing Kubernetes deployments during development, allowing you to focus on coding and testing your application. This setup provides a solid foundation for building more complex microservices and cloud-native applications.
