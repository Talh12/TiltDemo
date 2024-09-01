# Define the Docker build
docker_build('tilt-demo', './app')

# Load the Kubernetes deployment
k8s_yaml('kubernetes/deployment.yaml')

# Forward port 5000 on localhost to the container's port 5000
k8s_resource('tilt-demo', port_forwards=5000)
