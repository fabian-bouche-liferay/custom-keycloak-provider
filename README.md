# Custom keycloak provider

This plugin generates an email claim in OIDC tokens
by concatenating first name + "." + last name + "@test.com"
for a given authenticated user.

## Build

```gradlew build```

## Deploy

 - Stop keycloak
 - Copy build/libs/custom-keycloak-provider.jar to keycloak's providers directory
 - Restart keycloak

## Using the provider

 - Go to the keycloak client in the realm administration
 - Select the *Client scopes* tab
 - Select the *Dedicated scope and mappers for this client*
 - *Add Mapper* -> *By Configuration* and select *Custom Token Mapper*

You will name the mapper and the claim which will receive the custom
claim value.

You will also define which OIDC tokens will receive that custom claim.

Note: Liferay expects to read claims in the User Info Token.
