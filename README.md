# dd-integrations-in-docker
 
# Set Up Instructions

### 1. Create an Environmental Variale with your DD API Key

Create a temporary Environment Variable for you Datadog API Key:

```
export DD_API_KEY=<DD_API_KEY>
```
Here are directions on finding your [<DD_API_KEY> Datadog API](https://docs.datadoghq.com/account_management/api-app-keys/#add-an-api-key-or-client-token).

[This article](https://phoenixnap.com/kb/set-environment-variable-mac) is helpful in managing your Enviroment Variables. 

### 2. Initiate Docker Swarm

We will be using Docker swarm for this example. So you will need to initiate a docker swarm with:

```
docker swarm init
```
### 3. Download or Clone this repository

### 4. Deploy your swarm stack

You are now ready to deploy the Docker Swarm Stack which is defined in docker-compose.yml of the cloned/downloaded repository. You can deploy with the following command: 
```
docker stack deploy --compose-file=docker-compose.yml integration_stack
```

[This stackoverflow post](https://stackoverflow.com/questions/42139605/how-do-you-manage-secret-values-with-docker-compose-v3-1) is extreamly helpful in walking through the process of starting a swarm stack.





