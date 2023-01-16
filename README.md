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

## Usage
You will have to occasionally execute the `obtain registry token` request as the access token expires after 60 minutes.

Check the atlas-h2020-registry *collection* variable (not the *environment* variables). The `service_name` variable is meant to be filled manually. Other variables are typically fixed or dynamically updated by requests.

You can experiment with other requests to the [ATLAS registry APIs](https://sensorsystems.iais.fraunhofer.de/doc/?url=https://raw.githubusercontent.com/atlasH2020/atlas-registry-api/master/oas).

## Obtaining a service token
1. Set the `service_name` variable to the desired service.
2. Execute the `get service pairing` request
3. Select the `obtain service token` request, click the **Authorization** tab, and:
   1. Enter a valid URL in the *Callback URL* text input.
   2. Click the *Get New Access Token* button
   3. When prompted, enter a valid username and password.
   4. When successful, copy the value of *Access Token* from the **Token Details** dialog
4. You may now save the copied value in a postman service collection variable.
   1. You may also choose to copy the refresh_token and manually save it in the `service_refresh_token` collection variable.
   2. Access tokens are normally short-lived, typically 15-60 minutes and must be refreshed. You can achieve this by clicking the *Send* button in the request, assuming you had previously set the `service_refresh_token`.

