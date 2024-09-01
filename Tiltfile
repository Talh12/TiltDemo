docker_build('tilt-demo', './app')

k8s_yaml('kubernetes/deployment.yaml')

k8s_resource('tilt-demo', port_forwards=5000)
