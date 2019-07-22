# Devops Web App


### install the node packages for the web tier:
```sh
→ npm install
```
### start the app
```sh
→ npm start
```

###  NOTE this app uses two env variables:

- PORT: the listening PORT
- API_HOST: the full url to call the API app

These two variables need to be set 

## Create the Web tier of mu created ECS service 
```
cd web
mu -n node-3tier-app service push acceptance
mu -n node-3tier-app service deploy acceptance
mu -n node-3tier-app pipeline up
```
This creates the web container, web task, web service as well as the pipeline for building the web container in the AWS ECS acceptance cluster. It's necessary to create the web tier after the api and database tier because the health of the web container relies on recieving a response from the api service. 