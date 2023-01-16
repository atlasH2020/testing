# testing

## Setup
Download the [atlas-h2020-variables.postman_environment.json](./atlas-h2020-variables.postman_environment.json) environment and import it in postman.

Have a look at the variables; some of these must be defined to test specific services.

Download the [atlas-h2020-registry.postman_collection.json](./atlas-h2020-registry.postman_collection.json) collection and import it in postman.

in the environment globals, configure the following variables:

```
atlas_my_client_id=<enter your participants client id here>
atlas_my_client_secret=<enter your participants client secret here>
```

Now execute the `obtain registry token` request. If successful, the `registry_token` variable will have been automatically updated.

# Usage
You will have to occasionally execute the `obtain registry token` request as the access token expires after 60 minutes.

Check the atlas-h2020-registry *collection* variable (not the *environment* variables). The `service_name` variable is meant to be filled manually. Other variables are typically fixed or dynamically updated by requests.

You can now experiment requests to the [ATLAS registry APIs](https://sensorsystems.iais.fraunhofer.de/doc/?url=https://raw.githubusercontent.com/atlasH2020/atlas-registry-api/master/oas).