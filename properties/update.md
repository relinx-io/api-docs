# Update Property

## Request
* **URL**: `/auth/v1/properties/:propertyId`
* **Method**: `PUT`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `propertyId`: Property ID
* **Query Parameters**: None
* **Request Body**:
```json
{
    "property": {
        "title": string, // Title. Optional
        "note": string, // Note. Optional
        "dataType": number, // Property Data Type. See CONSTANTS. Optional
        "list": [ // List elements, when dataType = 5 (List). Optional
            {
                "id": string, // Element ID. Required
                "title": string, // Element title. Required
            },
            ...
        ]
    }
}
```

* **Sample Request Body**:
```json
{
    "property": {
        "title": "IP",
        "note": "IPv4 address",
        "dataType": 1
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:
None