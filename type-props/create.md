# Add Property to Type

## Request
* **URL**: `/auth/v1/type-props`
* **Method**: `POST`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**: None
* **Query Parameters**: None
* **Request Body**:
```yaml
{
    "typeProp": {
        "typeId": string, // Type ID. Required
        "propertyId": string, // Property ID. Required
        "isRequired": boolean // Flag for required. Required
    }
}
```

* **Sample Request Body**:
```yaml
{
    "typeProp": {
        "typeId": "RPoiDeFc6",
        "propertyId": "u_tgpRd7p",
        "isRequired": true
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:

```yaml
{
    "typeProp": {
        "id": string
    }
}
```

* **Sample Response Body**:

```yaml
{
    "typeProp": {
        "id": "oLldi0PVH"
    }
}
```
