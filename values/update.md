# Update Property Value of Item

## Request
* **URL**: `/auth/v1/values/:valueId`
* **Method**: `PUT`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `valueId`: Value ID
* **Query Parameters**: None
* **Request Body**:

```json
{
    "value": {
        "itemId": string, // Item ID. Optional
        "propertyId": string, // Property ID. Optional
        "value": string // Value. Optional
    }
}
```

* **Sample Request Body**:
```json
{
    "value": {
        "itemId": "XogKr3aya",
        "propertyId": "2Ezv8qpXi",
        "value": "updated value"
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:
None