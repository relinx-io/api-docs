# Update Type Property

## Request
* **URL**: `/auth/v1/type-props/:typePropId`
* **Method**: `PUT`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `typePropId`: TypeProperty ID
* **Query Parameters**: None
* **Request Body**:

```yaml
{
    "typeProp": {
        "typeId": string, // Type ID. Optional
        "propertyId": string, // Property ID. Optional
        "isRequired": boolean // Flag for required. Optional
    }
}
```

* **Sample Request Body**:
```yaml
{
    "typeProp": {
        "typeId": "RPoiDeFc6",
        "propertyId": "u_tgpRd7p",
        "isRequired": false
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:
None