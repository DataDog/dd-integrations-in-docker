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

[Cloning a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) on Github


### 4. Create Docker Secretes for usernames and passwords

You will want to create Docker Secrets for your user name and passwords. This can be done via 

```
 echo "<password>" | docker secret create my_password -
```

You will then need to update the services in the docker-compose.yml to reference the secrets you created. [This article](https://medium.com/@adrian.gheorghe.dev/using-docker-secrets-in-your-environment-variables-7a0609659aab) does a good job outlining the process. 



### 5. Deploy your swarm stack

You are now ready to deploy the Docker Swarm Stack which is defined in docker-compose.yml of the cloned/downloaded repository. You can deploy with the following command: 
```
docker stack deploy --compose-file=docker-compose.yml integration_stack
```


NOTE: you may see the following error:
```
Creating service integration_stack_<service_name>
failed to create service integration_stack_<service_name>: Error response from daemon: network integration_stack_default not found

```
If this occures, simply rerun the docker stack deploy command. You may need to rerun the command several times before it sucsessfully deployes. 


[This stackoverflow post](https://stackoverflow.com/questions/42139605/how-do-you-manage-secret-values-with-docker-compose-v3-1) is extreamly helpful in walking through the process of starting a swarm stack.




