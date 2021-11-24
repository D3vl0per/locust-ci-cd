# Auto locust load test config and worker distribution with Docker and GitHub Action

## Install
1. Fork the repo and change the visibility option to private
2. Set the environment variables (`DOCKER_API_TOKEN`, `DOCKER_LOGIN_NAME`, `DOCKER_REPO`) in the repository according to your external container image registry
3. Modify the `locustfile.py` config file as you like
4. Use the built image

## How I use it?
First of all, I test web applications in my current infrastructure with this solution.  
I currently use the Hetzner cloud provider for this task.  
I start a basic server for the master node and create a private network for it.  
To start worker servers in bulk, I make a basic worker server configuration. After that I will take a snapshot of it. Then from the snapshot I start several servers in the same network as the master server. After the worker servers are started, they automatically connect to the master server. 
If you change the configuration file in the repository, after CI/CD the watchtower service will replace the container image on all worker servers.

## Credit
https://github.com/locustio/locust
