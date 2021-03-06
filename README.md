# Keycloak Docker image with New Relic

Keycloak Server Docker image.
Current Support following versions of Keycloak
- 3.4.3.Final

## Usage
The usage is exactly same as [keycloak docker image](https://hub.docker.com/r/jboss/keycloak). 

A sample container with 
- Admin Credentials (user: `admin`, password: `admin`)
- Running on port `8180`
- With Valid `NEW_RELIC_LICENSE_KEY` and `NEW_RELIC_APP_NAME`

will run via following command

    docker run 
        -h keycloak.host 
        -e KEYCLOAK_USER=admin
        -e KEYCLOAK_PASSWORD=admin
        -e NEW_RELIC_APP_NAME=<APPNAME> 
        -e NEW_RELIC_LICENSE_KEY=<KEY> 
        --name keycloak 
        -p 0.0.0.0:8180:8080 
        fizzcorp/keycloak-newrelic:3.4.3.Final

Please note that `keycloak.host` will be the name of node that you see in new relic. 
Newrelic charges on the basis of number of instances pushing data to an application. 

# How to Contribute

If you don't see the keycloak version that you want to use with new relic, follow the following guidelines.
- Fork [this](https://github.com/hassantariq-carameltech/keycloak-newrelic) repo.
- See the content of Dockerfile.
- Replace keycloak version with the version of your choice.
- Edit New Relic Java Agent version (make sure that keycloak version and java agent version are compatible)
- Commit and Push your changes.
- Make a pull request.
- Your commit will be merged manually with respective tag in both docker image and github (tag addition via pull request is not avaiable on github yet 😃 ).


