# Relinx REST API Documentation

## Introduction
This repo contains [Relinx](https://relinx.io) REST API documentation.

To use this API please register at [Relinx](https://relinx.io) and add an API Key to your [account](https://app.relinx.io/account).

## API Keys
* API Keys are used to authenticate to the system, so keep your API Keys secret
* Only add an API Key to your account if you're using API access
* Remove unused API Keys
* Consider rotating API Keys periodically
* Regenerate API Keys on any suspicious activity
* API Keys are in the form `id.key`. For example `vHU8cOfU1YgxH6uS.qR5ZvjbVM4HkKQoQ-jLMX7mklAELsXdDb-OQB3BHHROyaZNLEJ-SMTKgiQ7O6UxNaWs-XcA3dan9G0jHPleV`
* We store the `id` part in plain text (for you to identify your keys) and the whole key hashed. The key is generated and shown to you in plain text only once. We're not able to recover it, so make sure to note it

## Versioning
* All APIs have a version (initially `v1`) specified in their URL
* Adding non-breaking changes such as optional field, required field with a default value, returning an extra value, etc, will not result in a new version
* New versions will be introduced on breaking changes (i.e. `v2`, `v3` and so on)
* We'll try to maintain backward compatibility as long as possible. In cases when it's not possible End-Of-Life date for a deprecated API will be announced
* Consider watching (and starring 😉) this repo to get notified on changes and addition of new APIs

## Usage
* Base URL to prefix all URLs in this documentation is [https://api.relinx.io](https://api.relinx.io)
* All APIs starting with the `/auth` prefix require the `Authorization` header to be set to "`ApiKey YOUR_API_KEY`"
* Nearly all APIs require `workspaceId` custom header to be set to the current Workspace ID. See [Get All Workspaces](workspaces/all.md) to get Workspace ID
* Common constants used by APIs are described in [CONSTANTS](CONSTANTS.md)
* Unless stated otherwise all `PUT` requests behave like `PATCH`, i.e. update only fields present in the request body and leave other fields intact
* `DELETE` operations are permanent, though the log is retained.

## Response Codes

### Success Codes
All successful requests unless stated otherwise return status code `200 OK`.

### Error Codes and Conditions
* `400 Bad request`
    * Missing required field in an entity
    * Duplicate entry
    * Non-existent entity referenced by a foreign key
    * Request malformed by any other means
* `401 Unauthorized`
    * Missing or invalid API Key
* `403 Forbidden`
    * Performing operation not permitted by user's tier
    * Performing operation not permitted by user's role
    * Making changes to a read-only Workspace data
* `404 Not found`
    * Updating or deleting non-existing entity
    * Invalid `workspaceId` Header
    * Invalid API URL
* `500 Internal Error`
    * Temporary issue with an API Server. Please try again after some time. Sorry for any inconvenience in advance
    * Permanent issue with an API Server. Please open an issue in this repo describing the problem. Sorry for any inconvenience in advance

## Postman Collection
* Download and import `Relinx.postman_collection.json` into Postman Collections
* Download and import `Relinx.postman_environment.json` into Postman Environments
* Select newly imported `Relinx` environment
* Set the `apiKey` variable in the `Relinx` environment. See [Account page](https://app.relinx.io/account)
* Set the `workspaceId` variable in the `Relinx` environment. See [Get All Workspaces](workspaces/all.md)

## API
* [Workspaces](workspaces)
    * [Get All Workspaces](workspaces/all.md)
* [Properties](properties)
    * [Get All Properties](properties/all.md)
    * [Create Property](properties/create.md)
    * [Update Property](properties/update.md)
    * [Delete Property](properties/delete.md)
* [Types](types)
    * [Get All Types](types/all.md)
    * [Get Single Type](types/single.md)
    * [Create Type](types/create.md)
    * [Update Type](types/update.md)
    * [Delete Type](types/delete.md)
* [Relations](relations)
    * [Get All Relations](relations/all.md)
    * [Create Relation](relations/create.md)
    * [Update Relation](relations/update.md)
    * [Delete Relation](relations/delete.md)
* [Type Properties](type-props)
    * [Add Property to Type](type-props/create.md)
    * [Update Type Property](type-props/update.md)
    * [Delete Property from Type](type-props/delete.md)
* [Type Links](type-links)
    * [Add Link between Types](type-links/create.md)
    * [Update Link between Types](type-links/update.md)
    * [Delete Link between Types](type-links/delete.md)
* [Items](items)
    * [Get All Items (Flat)](items/all-flat.md)
    * [Get Single Item](items/single.md)
    * [Create Item](items/create.md)
    * [Update Item](items/update.md)
    * [Delete Item](items/delete.md)
* [Values](values)
    * [Set Property Value of Item](values/create.md)
    * [Update Property Value of Item](values/update.md)
    * [Delete Property Value from Item](values/delete.md)
* [Links](links)
    * [Add Link between Items](links/create.md)
    * [Update Link between Items](links/update.md)
    * [Delete Link between Items](links/delete.md)

> For security reasons some APIs like manipulating Workspaces, Users, Members, API Keys, etc are not published.

## Support
For any questions, problems related to the API access please open an issue in this repo or send an email to support@relinx.io
