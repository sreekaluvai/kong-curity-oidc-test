## Getting Started

Create hosts entry for curity.kong.lan and proxy.kong.lan 

Get a curity license

### Upload kong license as openid-connect plugin is enterprise plugin
Upload the kong license to environment variable 

```cmd
  export KONG_LICENSE_DATA='<license>'
```

### start the containers using docker compose files

```cmd
  docker-compose up -d
```

### setting up curity

Login into curity http://localhost:6749/admin using the admin as username password from docker-compose file

Setup curity as detailed in https://curity.io/resources/learn/first-config/

Then upload curity-kong-config.xml and Merge it to the config and commit

### testing the changes

Try to consume http://proxy.kong.lan:8000/anything then it will redirect to the curity login page. Create an user account for the first time and login with it. 

If the authentication is successful, you can see the access_token in header Access-Token, id token in header Id-Token and introspection results in header x-into
