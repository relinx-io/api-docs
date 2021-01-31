# Create Property

## Request
* **URL**: `/auth/v1/properties`
* **Method**: `POST`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**: None
* **Query Parameters**: None
* **Request Body**:
```json
{
    "property": {
        "title": string, // Title. Required
        "note": string | null, // Note. Optional
        "dataType": number, // Property Data Type. See CONSTANTS. Optional, defaults to 1 (String)
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
        "title": "Vendor",
        "note": "Software vendor",
        "dataType": 5,
        "list": [
            { "id": "ms", "title": "Microsoft" },
            { "id": "rnx", "title": "Relinx" }
        ]
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:

```json
{
    "property": {
        "id": string
    }
}
```

* **Sample Response Body**:

```json
{
    "property": {
        "id": "oLldi0PVH"
    }
}
```
